<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Michael Nelms  
**Email:** michaelj.nelms@gmail.com

---

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

To get hands-on experience with AWS services, I completed a project focused on hosting a static website using Amazon S3. This gave me practical exposure to configuring buckets, managing access controls, and understanding how public website hosting works on S3.

### Tools and concepts

For this project, I worked with:
- **Amazon S3** for object storage and static hosting
- **Access Control Lists (ACLs)** to manage permissions on individual files
- **Bucket policies** to define global rules for access control at the bucket level

### Project reflection

This project took me approximately 5 minutes from start to finish. The AWS Management Console made it easy to navigate and set up, and the experience helped reinforce my understanding of how storage, access, and public hosting work together.

---

## How I Set Up an S3 Bucket

Creating an S3 bucket through the AWS Console was simple and quick.

I chose the **us-east-1 (N. Virginia)** region. This is the default AWS region when setting up new resources and offers low latency based on my geographic location.

I learned that **S3 bucket names must be globally unique** across all AWS accounts and regions. That means once a bucket name is taken by anyone, it cannot be used again, even in another account. I selected a unique name to avoid conflicts.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### index.html and image assets

I uploaded two essential files to my bucket:
- `index.html`: This file contains the core content and structure of the website.
- A `.zip` file: This contained supporting image assets that are used by the HTML file.

These files are necessary for the website to display correctly when accessed via the S3 endpoint. Uploading was straightforward using the AWS Console’s drag-and-drop interface.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

Website hosting in S3 allows you to serve static content such as HTML, CSS, and JavaScript directly from a bucket.

To enable this feature, I navigated to the **Properties** tab of the bucket and turned on **Static website hosting**. I specified `index.html` as the default root document.

To make the files publicly accessible, I had to configure permissions using **Access Control Lists (ACLs)**. ACLs let you control access to individual objects. I enabled public read access so that anyone can view the files.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

Once static website hosting was enabled, AWS provided a **bucket endpoint URL**. This is a public URL that can be used to access the website directly.

When I first visited the endpoint, I received a **403 Forbidden** error. This happened because the uploaded files were still private by default, even though hosting was enabled.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

To resolve the 403 error, I:
- Disabled **Block all public access** in the bucket settings.
- Applied **public-read ACLs** to both `index.html` and the image files.

After making these changes, I was able to successfully access the website through the S3 bucket’s public URL. This confirmed that the configuration was complete and permissions were working correctly.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

In addition to ACLs, S3 allows the use of **bucket policies** to define fine-grained access controls at the bucket level.

For this project, I experimented with a policy that **denies deletion of objects** in the bucket. After applying the policy, I tested it by attempting to delete the `index.html` file—and as expected, the action was denied due to the policy in place.

This helped me understand how bucket policies can enforce restrictions beyond basic ACLs and how they can be used to protect critical files from accidental deletion.

![Image](http://learn.nextwork.org/affectionate_gold_majestic_sloth/uploads/aws-host-a-website-on-s3_sm2sm2sm)

---

