---
layout: default
title: "Cover letter"
---
# HEY, 37Signals!
I'm Mansa Keïta, and I'm a 24-year-old self-taught programmer. I usually feel more comfortable
showing who I am than talking about it. So, I want to start this letter with something different by sharing the
story behind my most proud accomplishment, which is this [Rails
PR](https://github.com/rails/rails/pull/43399). (I took the liberty to include technical details
to explain my design decisions as if I was talking to a programmer.) Then, I will expand on why
you should hire me and why I want to work at 37Signals.

## The story
I was one year into my programming journey after I dropped out of college, and I came to a
point where I got tired of building simple [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) apps. I wanted to work on something meaningful,
but I didn't know what. I was desperately trying to find ideas but couldn't find anything that
interested me. I was trying to force the creative process, but good ideas come when you don't
look for them. 

I figured I needed to take a break from programming to get life experiences that would inspire
me. So, I started working as a volunteer in an association to teach kids the basics of
programming. During that time, I spent a lot of time working in a library because that's where
we were doing most of the animations. I saw the staff members using some software with some weird and
verbose [syntax](https://docs.owwl.org/pub/Evergreen/CatalogIdentifyingSuitableMarcRecords/igp_9bbc253943f5d383b94a607ba4d72ed9_MARC_Example_Book.png) to describe a simple book with lots of details. I found out that it was a format
that libraries use to describe the resource of their online catalog. Most libraries use
variations of what is called: MARC (MAchine Readable Cataloging). They use it to encode library
data to use it in a digital environment. So, I thought it could be a nice challenge to build an
app that generates an online catalog from MARC data. I finally had an idea of something to work
on, but little did I know what I was getting into. 

The complexity was overwhelming at first. I had to learn
about the MARC format and library cataloging. Once I became knowledgeable enough, I started
working on [modeling the domain](https://en.wikipedia.org/wiki/Domain_model#Overview) in the
context of a Rails app. That's when things started to become complex. I realized domain
modeling wouldn't be as easy as it is with simple CRUD apps. 

Working with MARC data is like working with HTML data. The structure of HTML documents can be
deeply nested, and the attributes of each tag are dynamic. We call this kind of data:
[semi-structured data](https://en.wikipedia.org/wiki/Semi-structured_data). Each type of
document is an example of semi-structured data. For example, an email is an example of
semi-structured data because the header is always structured with metadata like
sender, receiver, or object, but the content is highly dynamic. The last part
doesn't fit well with the [relational model](https://en.wikipedia.org/wiki/Relational_model)
used by [relational databases](https://en.wikipedia.org/wiki/Relational_database). What makes
relational databases powerful is the ability to ensure data integrity with a predefined
[schema](https://en.wikipedia.org/wiki/Database_schema) and make complex queries with
[joins](https://en.wikipedia.org/wiki/Join_(SQL)). But in this case, the things that make
relational databases powerful are the things that get in our way and complicate our model
instead of simplifying it. Using a static schema doesn't give us the flexibility to model data
with dynamic attributes. Using joins would be inefficient due to the deep level of nesting.
Imagine performing hundreds of joins to retrieve a single HTML document. We could argue that
we can store this in a text column. But for the purpose of my project, I needed to model the
dynamic part to generate hierarchical facets.

So, I started investigating [document databases](https://www.mongodb.com/document-databases) and realized how easy it would be to model
MARC data with them. Though it was appealing to switch to using a document database like MongoDB,
it meant that I wouldn't be able to get the benefits of using a relational database for the
parts of the model that fits in the relational model. I felt like making the switch would do
more harm than good in the long run.

After some thinking, I realized it might be possible to get the best of both worlds by using JSON to store
semi-structured data in relational databases like Postgres and MySQL. I could then use the
Attributes API to map Ruby classes to JSON columns to interact with the database as
ActiveRecord does. And that's how this [gem](https://github.com/mansakondo/activemodel-embedding) was born, which I later extracted into a [PR](https://github.com/rails/rails/pull/43399).

## Why should you hire me?
I'm sure you have plenty of talented candidates for this internship. So, I wanted to do
something special to differentiate myself. That's why I shared this story. The purpose was to show my ability to: 
- Solve an overwhelmingly complex problem with a simple, concise, and
elegant solution that allowed me to build my app the Rails way.
- Exercise my critical thinking to identify something missing in Rails and use my creativity to solve my own problem by extending it.
- Approach the problem from a higher perspective to avoid rabbit holes and make the right design decisions.

That's an example of what I can do when I'm working on something meaningful, and I would love
to have other opportunities to build software like that.

Another thing worth mentioning is that I became a Rails [contributor](https://contributors.rubyonrails.org/contributors/mansakondo/commits), and I would love to have the opportunity to contribute to Hotwire in the future.

## Why 37Signals?
For me, this internship at 37Signals is an opportunity to:
- Solve meaningful problems and possibly extract some solutions in Rails or Hotwire
- Use modern technologies like Hotwire to work on innovative products like HEY.
- Work in an environment that will challenge me and unleash my potential.

But more than that, it will be an opportunity to work in a company whose influence shaped me into the
programmer I am today. So, in a way, it will be an opportunity to give back.

37Signals is the reason I am where I am in my programming journey. It started when I
discovered Rails after trying to learn web development with Django without much success.
That's how I came across Ruby. I immediately fell in love with it. The syntax was so
expressive, concise, and elegant. I knew that I wanted to write Ruby code for a living.

Discovering Rails led me to find out about its creator, David Heinemeier Hansson. His influence
shaped the way I see and approach software writing. I began to see it more like an art than a
science. I became passionate about software design and domain modeling, and I started to care
more about the clarity and expressiveness of the code rather than the algorithms and
performance.

But this influence grew beyond software writing when I read Getting Real and ShapeUp. Jason
Fried and Ryan Singer shaped the way I think about how software should be built. I began to
appreciate the value of constraints to focus on what matters to get things done. I began to see
that what makes an API design great is the same thing that makes a UI design great. I have
learned that great interfaces should clearly communicate opportunities for action
(*affordances*) users can take to achieve their goals. In that regard, the work of a programmer
and a designer is very similar.

I also read the Rework. I never read and re-read a book that quick :) I have learned from that
book that ideas should not be forced but should emerge out of necesity. I have learned that
great ideas comes from our ability to turn the frustrations of today into the innovations of
tomorrow. This gave me the confidence to innovate and start my own tech company one day.

In a sense, we can say that I was raised by the culture of 37Signals since the beginning of my
journey. So, I'm pretty much the definition of culture fit :)

## Thanks for reading
Thank you for taking the time to read me this letter, and we will see what the future has in
store for me.

*Mansa Keïta*
