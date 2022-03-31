---
sidebar_label: "Part 1: Set up"
sidebar_position: 0
---

# Thinking out loud

Throughout this page, I'm just taking notes as I complete the tasks provided by Muskaan. I'm narrating my decisions as I go through the requested steps and asking myself questions out loud.

## Data Models & Authorization

The first step after creating an instance on Hasura cloud is to add an example from the [Hasura Data Hub](https://hasura.io/data-hub/data-models-and-authorization/).

- I'm going to go with the "one-to-many" relationship example
- I'm using this because the relationships between tables - and data - is a huge draw for developers migrating to GraphQL
- This should be one of the clearest and easiest-to-follow pieces of documentation
- I like the cards on the [Data Models and Authorization](https://hasura.io/data-hub/data-models-and-authorization/) page
- Not a fan of the truncated text, though: for an inexperienced user, most descriptions are cut off before revealing enough information to make an accurate decision

## Relationships: One-to-Many

When I land on [this data model's page](https://hasura.io/data-hub/data-models-and-authorization/schema-share-relationships-one-to-many/), I'm hit with a lot of information at once. There's visual hierarchy present, but there's also a fair amount of cognitive strain due to a few issues:

### Inconsistent data

The example references creating a relationship between two tables: `author` and `passport`. However, as the example continues, the table shifts from `passport` to what - presumably - is correct: `articles`.

From the standpoint of professionalism, a small typo like this sticks out to me. If I'm a new user - with a decent understanding of the principles being used - reading through these docs, that's going to be an immediate tick **against** Hasura. It just feels sloppy.

However, if I'm a new user that's trying to learn about GraphQL and data modelling, I'm just plain confused.

Either way, I'm an unsatisfied user who's starting to associate my frustrations with the product.

### Visuals

I like the database diagram. It provides a clear illustration of these two tables. However, a first-time user may not understand the `author_id` property as the foreign key connecting the two. Some more context would be helpful here.

### Hyperlinks

Why are the links, underneath the diagram, to the source code and tutorials not clickable? I understand they're present in the card on the right-hand side under the "relevant links" heading, but this redundancy doesn't make sense to me. I also understand this is probably related to the page's data being pulled from the repo.

I could see someone (read: me 🙋🏽‍♂️) copying/pasting these links and then getting a bit annoyed when - later - clicking on the links in the card takes me to the same destination(s).

## Try It Out

Clicking on the CTA takes me to [this repo](https://github.com/hasura/template-gallery/tree/main/postgres/relationships-one-to-many). My first reaction is a bit of annoyance that the `README.md` is the **same** information present on the data model's page. It feels like I'm in a loop.

If I'm someone with less experience, I've just encountered more friction. I don't think most new(er) users would be adept enough to dig into the files in the repo and find the `migration.sql` document.

:::info

Unexpected Easter egg! [Martin](https://github.com/martin-hasura), who authored this `sql` document, helped me via Twitter with a DO droplet issue last year. Small world.

:::

## The `migration.sql` document

I'm in the [aforementioned document](https://github.com/hasura/template-gallery/blob/main/postgres/relationships-one-to-many/migration.sql). I think **novelty** is a key component of engagement. I love the idea of using the _Back to the Future_ quotations.

However, I think there's a few key issues this raises.

1. We're trying to help developers understand the relationship between two tables: `author` and `articles`.
2. We've now introduced a third taxonomy: `quotations`. While this isn't said explicitly, it's something that's adding to the cognitive load of anyone reading the document/trying to apply its concepts.

## Running the SQL

Throughout both documents, this quotation comes up.

> This schema is installable through your Hasura Console

However, there's no guidance provided. Again, I think it's a jump for someone landing on the repo to find the `migration.sql` document and know to...

1. head to their cloud instance
2. go to the data tab
3. find the SQL button
4. paste the code

I went ahead and followed those steps, since I've used the `sql` feature in Hasura before, and achieved the desired result.

## Wrapping up

Overall, I see a lot of great opportunities for improvement to help clarify these docs for users. In the next section, you'll see me focus on a few suggestions for improvement. All of these concepts are grounded in the goal of making the docs as accessible and useful for as many users as possible.
