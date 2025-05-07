# AWS NLP Video Dashboard 📺🔍

This project was built as part of the AWS Academy Capstone for Natural Language Processing. It demonstrates an end-to-end data engineering and NLP workflow using AWS services and Python to generate a searchable video content dashboard.

## Business Scenario

You work for a training organization offering an ML course with over 40 video lessons. The goal: create a tool that allows students to search and view specific ML topics by extracting and analyzing key phrases from the videos.

## Tech Stack

- **AWS Services**:
  - Amazon S3 – storage for videos and artifacts
  - Amazon Transcribe – audio transcription from video files
  - Amazon Comprehend – key phrase extraction
  - AWS IAM – secure access roles
- **Data Tools**:
  - Python (Boto3, Pandas, JSON, Matplotlib)
  - Jupyter Notebooks (via SageMaker)

## ETL Pipeline

1. **Ingest Videos**  
   Video content loaded into an S3 bucket.

2. **Transcribe Audio**  
   AWS Transcribe jobs are run across all video files.

3. **Normalize Text**  
   Raw transcript data is cleaned and lowercased, punctuation is removed.

4. **Extract Key Phrases**  
   Comprehend identifies relevant keywords and topics from normalized transcripts.

5. **Visualize Results**  
   A bar chart displays the most frequent key phrases across all videos.

## Example Output

![Top Phrases Chart](sample_outputs/top_phrases_bar_chart.png)

## Running This Project

### Prerequisites

- AWS account with:
  - Access to S3, Transcribe, Comprehend
  - An IAM role with the necessary permissions
- Jupyter Notebook environment (e.g., SageMaker or local)

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/aws-nlp-video-dashboard.git
   cd aws-nlp-video-dashboard

2. Upload videos to S3
Place MP4 files in a folder such as s3://your-bucket/video/.

3. Run notebooks in order
Each step of the pipeline is broken into a dedicated notebook in the /notebooks directory:

    1_transcribe_videos.ipynb

    2_normalize_text.ipynb

    3_extract_key_phrases.ipynb

    4_visualize_dashboard.ipynb

## IAM Role ##
    
    arn:aws:iam::533267341463:role/service-role/c144972a3751929l10036967t1-ComprehendDataAccessRole-NMmV7kHNIjDG

Ensure your role grants access to:

    S3 (read/write)

    Transcribe

    Comprehend
