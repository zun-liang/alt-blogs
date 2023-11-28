---
layout: post
title: Firestore Data Structure
---

<p>While developing this website, I discovered that Firestore offers an exceptionally flexible data structure, closely resembling a JSON tree with multiple layers of hierarchy. The structure consists of collections containing documents, each of which has fields and subcollections, as exemplified below:</p>
<pre><code>  collection {
    doc1 {
        field1: data,
        field2: data,
        field3: data,
        ...
        subcollection1 {
            doc1 {
                field1: data,
                field2: data,
                ...
                subcollection {
                    ...
                }
            },
            doc2 {
                ...
            }
        },
        subcollection2 {
            ...
        }
    },
    doc2 {
        ...
    },
    doc3 {
        ...
    }
    ...
  }
</code></pre>
<p>For my "blogs" collection, I've structured it in a way that suits my project's requirements:</p>
<pre><code>blogs {

<p>  blog_1 {
    id: blog_1_id,
    title: blog_1_title,
    overview: blog_1_overview,
    content: blog_1_content,
    timestamp: blog_1_timestamp,
    tag: {blog_1_tag1, blog_1_tag2, blog_1_tag3...},
    likes {
        likes {
              likes: blog_1_likes,
            }
        },
    comments {
      comment_1 {
                id: comment_1_id,
                name: comment_1_name,
                text: comment_1_text,
                timestamp: comment_1_timestamp,
      },
      comment_2 {
          ...
      },
      comment_3 {
          ...
      },
    },
    },</p>
<p>  blog_2 {
      ...
  },</p>
<p>  blog_3 {
      ...
  }
  ...
  }</p></code></pre>
<p>This data structure is effective for managing data and establishing security rules in line with the specific needs of my project.</p>
