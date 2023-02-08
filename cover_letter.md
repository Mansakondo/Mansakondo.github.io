---
layout: default
title: "Cover letter"
---
# HEY, 37Signals!
I'm Mansa Keïta, and I'm a 24-year-old self-taught software writer. I usually feel more comfortable
showing what I can do than talking about it. So, I'll try to paint a clear picture of
myself in this letter.

## How I work
The way I work is a little bit usual. Though I'm a programmer, I'm always trying to spend as
less time as possible in front of my computer. In fact, my primary working tools are my pen and my
notebook.

When I have a project idea, I like to write down what's flowing through my mind without trying
to organize it. This allows me to embrace the chaos I need for order to emerge on its own. We
can't force ourselves to understand or find an effective way to structure something because
these things are consequences of a change of perspective. So, as I'm taking my notes, my
perspective changes, and I'm starting to make new connections and discover some structure, like
when solving puzzles.

I like to write pieces of code in my notes as they come to me and put the pieces together in
my mind. Then after letting my ideas grow in my mind, I already have a pretty good
idea of what I want to do, so typing the code becomes straightforward.

That's how I designed this [Rails PR](https://github.com/rails/rails/pull/43399), so I thought
that it would interesting to share the process behind it.

Note: I included technical details to explain my design decisions as if I
was talking to a programmer.

## The story behind my most proud accomplishment
I was one year into my programming journey after I dropped out of college, and I came to a
point where I got tired of building simple [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) apps. I wanted to work on something meaningful,
but I did not know what. I was desperately trying to find ideas but couldn't find anything that
interested me. I was trying to force the creative process, but good ideas come when you don't
look for them.

I figured I needed to take a break from programming to get life experiences that would inspire
me. So, I started working as a volunteer in an association to teach kids the basics of
programming. During that time, I spent a lot of time working in a library because that's where
we were doing most of the animations. I saw the staff members using software with weird and
verbose [syntax](https://docs.owwl.org/pub/Evergreen/CatalogIdentifyingSuitableMarcRecords/igp_9bbc253943f5d383b94a607ba4d72ed9_MARC_Example_Book.png) to describe a simple book with lots of details. I found out that it was a format
that libraries use to describe the resource of their online catalog. Most libraries use
variations of what is called: MARC (MAchine Readable Cataloging). They use it to encode library
data for use in a digital environment. So, I thought it could be a nice challenge to build an
app that generates an online catalog from MARC data. I finally had an idea of something to work
on, but little did I know what I was getting into.

The complexity was overwhelming at first. I had to learn about the MARC format and library
cataloging. Once I became knowledgeable enough, I started working on [modeling the
domain](https://en.wikipedia.org/wiki/Domain_model#Overview) in the context of a Rails app.
That's when things started to become complex. I realized domain modeling wouldn't be as easy as
it is with simple CRUD apps.

Working with MARC data is like working with HTML data. The structure of HTML documents can be
deeply nested, and the attributes of each tag are dynamic. We call this kind of data:
[semi-structured data](https://en.wikipedia.org/wiki/Semi-structured_data). Each type of
document is an example of semi-structured data. For example, an email is an example of
semi-structured data because the header is always structured with metadata like
sender, receiver, or object, but the content is highly dynamic. This last part
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

## Why should you hire me? Why 37Signals?
I'm sure you have plenty of talented candidates for this internship. So, I wanted to do
something special to differentiate myself. That's why I shared this story. The purpose was to show my ability to:
- Solve an overwhelmingly complex problem with a simple, concise, and
elegant solution that allowed me to build my app the Rails way.
- Exercise my critical thinking to identify something missing in Rails and use my creativity to solve my problem by extending it.
- Approach the problem from a [higher perspective](https://basecamp.com/shapeup/1.1-chapter-02#steps-to-shaping) to avoid [rabbit holes](https://basecamp.com/shapeup/1.4-chapter-05) and make the right design decisions.

This PR is an example of what I can do when I work on something meaningful, and I would love
to have other opportunities to write software like that.

Another thing worth mentioning is that I became a Rails [contributor](https://contributors.rubyonrails.org/contributors/mansakondo/commits), and I would love to have the opportunity to contribute to Hotwire in the future.

For me, this internship at 37Signals is an opportunity to:
- Solve meaningful problems and possibly extract open-source solutions.
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
more about the clarity and expressiveness of the code I was writing.

But this influence grew beyond software writing when I read Getting Real and ShapeUp. Jason
Fried and Ryan Singer shaped my perspective on how software should be built. I began to
appreciate the value of [constraints](https://basecamp.com/shapeup/1.2-chapter-03) to focus on
what matters to get things done. I began to see that what makes an API design great is the same
thing that makes a UI design great. Because great interfaces should clearly communicate
opportunities for action
([*affordances*](https://basecamp.com/shapeup/3.2-chapter-11#affordances-before-pixel-perfect-screens))
users can take to achieve their goals. In that regard, the work of a programmer and a designer
is very similar.

When I read Rework, I learned that ideas should not be forced but should emerge out of
necessity. I've learned that great ideas come from our ability to turn the frustrations of
today into the innovations of tomorrow. This gave me the confidence to innovate and start my
own tech company one day.

In a sense, we can say that I was raised by the culture of 37Signals since the beginning of my
journey. So, I feel like I'm an example of a cultural fit.

## Bonus: What I'm passionate about
I'm passionate about becoming better at solving problems and learning new skills in general.

As I started Jiu-Jitsu recently, I began to search for ways to develop skills faster and better. This
led me to find out about what is called the: *ecological approach to skill acquisition*. This
approach comes from the premise that we don't become skillful by repeating the same solution to
solve a problem in a specific situation but by repeating the process of solving the same
problem in different situations.

This approach involves using the *constraints-led approach* to design practice
with constraints that will allow people to self-organize and come up with effective solutions.
This reminds me of the ShapeUp method because it's also based on setting constraints to allow
teams to self-organize and be effective.

If you find that interesting, here are some videos to get started:
- [The Two Skill Acquisition Approaches: Key Differences](https://www.youtube.com/watch?v=cCsezh7ijzs)
- [Key Principles of the EcologicalApproach to Skill](https://www.youtube.com/watch?v=-TUjKAwc9Z8.)

## Thanks for reading
Thank you for taking the time to read this letter, and we'll see what the future has in
store for me.

*Mansa Keïta*
