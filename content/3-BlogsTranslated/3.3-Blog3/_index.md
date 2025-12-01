---
title: "Blog 3"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# Dynamically Configuring Job Settings with AWS Elemental MediaConvert

AWS Elemental MediaConvert is a powerful video transcoding service that enables media organizations to convert video content into multiple formats optimized for different platforms and devices. While basic transcoding is straightforward, many production workflows require dynamic configuration of job settings based on input content characteristics, business rules, or customer requirements. This blog explores strategies for dynamically configuring MediaConvert jobs to create flexible, scalable video processing pipelines.

---

## Understanding AWS Elemental MediaConvert

AWS Elemental MediaConvert is a file-based video transcoding service designed for video-on-demand (VOD) workflows. It converts video content from source formats into multiple output formats suitable for different delivery platforms.

**Key Features:**

- **Flexible Input/Output**: Supports 40+ input and output video formats
- **Quality Processing**: Industry-leading video quality at lower bitrates
- **Batch Processing**: Process multiple files efficiently
- **Advanced Features**: Motion graphics, audio mixing, caption handling
- **Scalability**: Handle unlimited concurrent transcoding jobs
- **Cost-Effective**: Pay only for the content you process

**Common Use Cases:**

- Video-on-demand content preparation
- Multi-quality format creation for adaptive streaming
- Archive format conversion
- Content normalization across platforms
- Live event post-processing and archival

---

## The Challenge: Static vs. Dynamic Configuration

### Traditional Static Configuration

Most organizations start with static job templates that define fixed output specifications. While simple to implement, static configurations have limitations:

**Limitations:**

- Cannot adapt to different input video characteristics
- One-size-fits-all approach may waste resources
- Difficult to accommodate diverse content types
- Manual adjustments required for special cases
- Limited ability to optimize for business requirements

**Example Static Scenario:**
All videos encoded at 1080p/30fps at 5 Mbps regardless of:

- Original resolution (could be 720p or 4K)
- Original frame rate (24fps, 25fps, 60fps)
- Content type (animation vs. live action)
- Target platforms (mobile, web, TV)

### Dynamic Configuration Approach

Dynamic configuration adapts transcoding parameters based on input content and business rules, providing:

**Advantages:**

- Optimizes quality for each unique input
- Reduces unnecessary processing costs
- Enables content-aware encoding
- Supports multiple delivery profiles
- Automates complex decision-making
- Scales efficiently across diverse content

---

## Architecture for Dynamic MediaConvert Configuration

### High-Level Workflow

```
Input Analysis
    ↓
Extract Metadata
    ↓
Apply Business Rules
    ↓
Generate Job Configuration
    ↓
Submit MediaConvert Job
    ↓
Monitor & Track
    ↓
Archive & Distribute
```

### Components

**1. Input Monitoring**

- S3 event notifications trigger workflow
- CloudWatch Events monitor source bucket
- EventBridge routes events to processing pipeline

**2. Content Analysis**

- Lambda function analyzes input video properties
- MediaInfo or FFmpeg extracts detailed metadata
- Determines resolution, frame rate, codec, bitrate

**3. Decision Engine**

- AWS Step Functions orchestrates workflow
- Evaluates metadata against business rules
- Selects appropriate output profiles
- Determines quality parameters

**4. Job Configuration**

- Builds dynamic MediaConvert job definition
- Applies quality presets based on analysis
- Configures multiple outputs for different platforms
- Sets up error handling and notifications

**5. Job Submission**

- Submits configured job to MediaConvert
- Tracks job progress and status
- Implements retry logic for failures

**6. Post-Processing**

- Move completed files to distribution locations
- Update content catalog/database
- Trigger downstream workflows
- Generate delivery manifests

---

## Implementation Strategies

### Strategy 1: Resolution-Based Configuration

Adapt output quality based on input resolution to avoid upscaling.

**Decision Logic:**

```
If input resolution >= 4K (2160p):
  - Create 4K, 1080p, 720p outputs
  - Use higher bitrates for quality preservation

Else if input resolution >= 1080p:
  - Create 1080p, 720p, 480p outputs
  - Standard bitrate allocation

Else if input resolution >= 720p:
  - Create 720p, 480p, 360p outputs
  - Lower bitrates appropriate for source

Else (< 720p):
  - Create single output at source resolution
  - Minimal bitrate to avoid quality loss
```

**Benefits:**

- Prevents unnecessary upscaling artifacts
- Optimizes bitrate allocation
- Reduces processing for lower-resolution content
- Improves storage and delivery efficiency

### Strategy 2: Frame Rate Normalization

Handle variable input frame rates intelligently.

**Decision Logic:**

```
Extract input frame rate

If frame rate == 23.976 fps (film):
  - Output at 24fps or 25fps
  - Apply appropriate pulldown

If frame rate == 29.97 fps (NTSC):
  - Output at 30fps standard

If frame rate == 59.94 fps (NTSC 60):
  - Output at 60fps
  - Create 30fps variant for compatibility

If frame rate is variable:
  - Normalize to closest standard
  - Flag for manual review if uncertain
```

**Benefits:**

- Handles broadcast frame rates correctly
- Creates compatible outputs for all platforms
- Prevents playback timing issues
- Reduces file size where possible

### Strategy 3: Content-Type-Based Configuration

Different content types require different encoding strategies.

**Content Detection:**

```
Analyze content characteristics:
  - Scene complexity (histogram analysis)
  - Motion detection (optical flow)
  - Bitrate consistency (texture analysis)
  - Black frames (scene detection)

Classify as:
  - Animated/Simple (lower bitrate adequate)
  - Standard video (moderate bitrate)
  - High-motion sports/action (higher bitrate)
  - Talking-head/static (lower bitrate)
```

**Encoding Parameters:**

```
Animated Content:
  - Lower bitrate (2-4 Mbps for 1080p)
  - Moderate GOP size (8-10 seconds)
  - Simple encoding profile

Live Action:
  - Standard bitrate (5-8 Mbps for 1080p)
  - Balanced GOP size
  - Balanced encoding

High-Motion:
  - Higher bitrate (8-12 Mbps for 1080p)
  - Shorter GOP (6-8 seconds)
  - Advanced encoding profile
```

### Strategy 4: Multi-Platform Output Configuration

Generate optimized outputs for different delivery platforms.

**Platform Profiles:**

```
Web (Responsive):
  - 1920x1080 @ 6 Mbps H.264
  - 1280x720 @ 3 Mbps H.264
  - 854x480 @ 1.5 Mbps H.264

Mobile (Bandwidth-Constrained):
  - 1280x720 @ 2.5 Mbps H.264
  - 854x480 @ 1 Mbps H.264
  - 640x360 @ 500 kbps H.264

TV/Premium (High-Quality):
  - 3840x2160 @ 20 Mbps HEVC
  - 1920x1080 @ 8 Mbps HEVC
  - 1280x720 @ 4 Mbps HEVC

Social Media (Quick Share):
  - 1280x720 @ 2.5 Mbps
  - Square format 1080x1080 @ 2.5 Mbps
  - Vertical 1080x1920 @ 2.5 Mbps
```

---

## Building the Decision Engine with AWS Step Functions

### Workflow Definition

```json
{
  "StartAt": "AnalyzeInput",
  "States": {
    "AnalyzeInput": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:region:account:function:AnalyzeVideo",
      "Next": "EvaluateRules"
    },
    "EvaluateRules": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:region:account:function:EvaluateBusinessRules",
      "Next": "SelectProfile"
    },
    "SelectProfile": {
      "Type": "Choice",
      "Choices": [
        {
          "Variable": "$.resolution",
          "StringEquals": "4K",
          "Next": "Configure4KOutput"
        },
        {
          "Variable": "$.resolution",
          "StringEquals": "1080p",
          "Next": "Configure1080pOutput"
        },
        {
          "Variable": "$.resolution",
          "StringEquals": "720p",
          "Next": "Configure720pOutput"
        }
      ],
      "Default": "ConfigureDefaultOutput"
    },
    "Configure4KOutput": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:region:account:function:Build4KJobDefinition",
      "Next": "SubmitJob"
    },
    "Configure1080pOutput": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:region:account:function:Build1080pJobDefinition",
      "Next": "SubmitJob"
    },
    "Configure720pOutput": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:region:account:function:Build720pJobDefinition",
      "Next": "SubmitJob"
    },
    "ConfigureDefaultOutput": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:region:account:function:BuildDefaultJobDefinition",
      "Next": "SubmitJob"
    },
    "SubmitJob": {
      "Type": "Task",
      "Resource": "arn:aws:states:::mediaconvert:createJob.sync",
      "Next": "JobSuccess"
    },
    "JobSuccess": {
      "Type": "Succeed"
    }
  }
}
```

### Analysis Lambda Function

```python
import json
import boto3
import subprocess

mediaconvert = boto3.client('mediaconvert')

def lambda_handler(event, context):
    bucket = event['detail']['bucket']['name']
    key = event['detail']['object']['key']

    # Get file information
    s3_uri = f"s3://{bucket}/{key}"

    # Extract metadata using ffprobe
    metadata = extract_metadata(s3_uri)

    return {
        'statusCode': 200,
        'bucket': bucket,
        'key': key,
        'resolution': metadata['resolution'],
        'frameRate': metadata['frameRate'],
        'codec': metadata['codec'],
        'bitrate': metadata['bitrate'],
        'duration': metadata['duration'],
        'contentType': classify_content(metadata)
    }

def extract_metadata(s3_uri):
    # Use ffprobe to get detailed metadata
    cmd = [
        'ffprobe', '-v', 'error',
        '-select_streams', 'v:0',
        '-show_entries',
        'stream=width,height,r_frame_rate,codec_name,bit_rate',
        '-of', 'csv=p=0',
        s3_uri
    ]

    output = subprocess.check_output(cmd).decode('utf-8')
    parts = output.strip().split(',')

    width, height = int(parts[0]), int(parts[1])
    resolution = determine_resolution(width, height)

    return {
        'resolution': resolution,
        'width': width,
        'height': height,
        'frameRate': float(parts[2]),
        'codec': parts[3],
        'bitrate': int(parts[4]) if parts[4] else 0,
        'duration': get_duration(s3_uri)
    }

def determine_resolution(width, height):
    if width >= 3840 or height >= 2160:
        return '4K'
    elif width >= 1920 or height >= 1080:
        return '1080p'
    elif width >= 1280 or height >= 720:
        return '720p'
    else:
        return 'SD'

def classify_content(metadata):
    # Simplified classification
    # In production, use more sophisticated analysis
    if metadata['bitrate'] < 1000000:  # < 1 Mbps
        return 'animation'
    elif metadata['frameRate'] > 50:
        return 'highmotion'
    else:
        return 'standard'
```

---

## Real-World Use Cases

### Use Case 1: Video Content Platform

**Scenario**: Streaming platform receives user-uploaded content

**Workflow**:

1. User uploads video
2. System analyzes video properties
3. Based on resolution and duration:
   - Determine appropriate quality ladder
   - Select encoding profiles
4. Generate multiple outputs for adaptive streaming
5. Create thumbnails and preview images
6. Update content database

**Result**: Each video optimized for its characteristics, reducing storage and delivery costs.

### Use Case 2: News and Media Organization

**Scenario**: Multiple content sources with varying specifications

**Workflow**:

1. Video ingested from broadcast feed, satellite feed, or social media
2. Analyze incoming video format and quality
3. Normalize to organization standards
4. Create archive version and broadcast-ready versions
5. Automatically distribute to appropriate platforms

**Result**: Consistent output quality across diverse sources.

### Use Case 3: Live Event Archival

**Scenario**: Live broadcast needs immediate on-demand availability

**Workflow**:

1. Live stream captured and recorded
2. Post-broadcast analysis of recorded file
3. Optimize encoding based on actual content
4. Create multiple quality variants
5. Update VOD catalog
6. Distribute to platforms

**Result**: On-demand content ready quickly with optimal quality/size tradeoff.

---

## Best Practices for Dynamic Configuration

### 1. Metadata Extraction

- Use reliable tools (FFmpeg, MediaInfo)
- Cache results to avoid re-analysis
- Handle errors gracefully
- Store metadata for future reference

### 2. Business Rules Engine

- Keep rules version-controlled and documented
- Implement A/B testing for new rules
- Monitor rule effectiveness and adjust
- Allow manual overrides when needed

### 3. Job Configuration

- Use job templates as base
- Programmatically modify only what's necessary
- Validate configurations before submission
- Implement dry-run capability

### 4. Error Handling

- Implement retry logic with exponential backoff
- Log detailed error information
- Create fallback configurations
- Alert on repeated failures

### 5. Monitoring and Optimization

- Track metrics: processing time, cost, quality
- Monitor encoder utilization
- Identify optimization opportunities
- Continuously refine rules based on data

### 6. Cost Optimization

- Right-size outputs based on content
- Avoid unnecessary quality levels
- Use tiered pricing for different content types
- Archive non-critical versions to Glacier

---

## AWS Services Integration

| Service        | Purpose                              |
| -------------- | ------------------------------------ |
| S3             | Source and output storage            |
| EventBridge    | Trigger workflow on file upload      |
| Lambda         | Content analysis and rule evaluation |
| Step Functions | Orchestrate workflow                 |
| MediaConvert   | Perform video transcoding            |
| CloudWatch     | Monitor metrics and logs             |
| SNS            | Send notifications                   |
| DynamoDB       | Store configuration rules            |
| CloudFormation | Infrastructure as code               |

---

## Performance Considerations

### Processing Efficiency

| Factor           | Impact                                     |
| ---------------- | ------------------------------------------ |
| Input Resolution | Higher resolution requires more processing |
| Duration         | Longer videos take proportionally longer   |
| Output Count     | Each output adds processing time           |
| Complexity       | More outputs = longer job time             |

### Cost Optimization

```
Cost Factors:
- Processing time (largest cost component)
- Output resolution (higher = higher cost)
- Number of outputs (linear scaling)
- Premium features (advanced encoding, captions)

Cost Reduction:
- Analyze input to avoid unnecessary outputs
- Skip outputs not needed for distribution
- Use efficient codecs (HEVC vs H.264)
- Schedule transcoding during off-peak hours
```

---

## Troubleshooting and Monitoring

### Common Issues

**Issue: Incorrect Resolution Detection**

- Solution: Validate metadata extraction
- Solution: Implement manual override capability
- Solution: Review sample outputs for accuracy

**Issue: Job Configuration Errors**

- Solution: Validate job definition before submission
- Solution: Implement schema validation
- Solution: Test with sample files

**Issue: Performance Bottlenecks**

- Solution: Monitor Step Functions execution time
- Solution: Parallelize independent tasks
- Solution: Optimize metadata extraction

**Issue: Unexpected Costs**

- Solution: Track output configurations
- Solution: Monitor number of jobs and outputs
- Solution: Review and optimize rules regularly

---

## Conclusion

Dynamically configuring AWS Elemental MediaConvert jobs enables organizations to:

- **Optimize Quality**: Adapt encoding to input content characteristics
- **Reduce Costs**: Eliminate unnecessary processing and storage
- **Scale Efficiently**: Handle diverse content types automatically
- **Improve Automation**: Reduce manual intervention and errors
- **Enable Innovation**: Support new platforms and formats easily

By combining AWS Elemental MediaConvert with Lambda, Step Functions, and intelligent decision engines, media organizations can build sophisticated, scalable video processing pipelines that adapt to business needs and content characteristics.

The future of video transcoding is intelligent, automated, and optimized—making MediaConvert's dynamic configuration capabilities essential for modern media workflows.
