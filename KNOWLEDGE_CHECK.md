
# Lab 07: Knowledge check


## Question 1: EC2 - Why can't I log in with SSH?

**Your answer:**

I went to EC2 → Security Groups → launch-wizard-1 → Inbound rules. This shows which incoming connections are allowed, including SSH traffic on port 22, which needs to permit access from my IP address.

## Question 2: Lambda - Why didn't my function run?

**Your answer:**

I went to Lambda → Functions → book-analyzer-dev-analyze_new_book → Function overview. This shows the S3 trigger connected to my public-hvs7nb bucket, which starts the function whenever a new .txt file is uploaded.

## Question 3: Lambda - Where do I find the error?

**Your answer:**

I went to Lambda → Functions → book-analyzer-dev-analyze_new_book → Monitor → View CloudWatch logs, then opened the log stream for the invocation. I can check the processing message for pg74.txt and look for any errors that occurred during execution.

## Question 4: EC2 or Lambda - A backlog or new uploads?

**Your answer:**

**Case A (5,000 existing books):** I would use EC2 because I can process the entire backlog as one batch job and terminate the instance afterward to avoid unnecessary costs.

**Case B (New uploads throughout the day):** I would use Lambda because it automatically processes each new book when it's uploaded to S3. It doesn't require a server to run continuously, making it more efficient for occasional uploads.

