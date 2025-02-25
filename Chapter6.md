# Contextual Discovery: The Lost Art of Domain Mapping

## Beyond the Surface: Understanding Your True Business Domain

In the relentless pursuit of digital transformation, organisations consistently make one catastrophic error: they begin building solutions before they truly understand the problem domain. The consequences are predictable and devastating—systems that don't align with business realities, teams that can't communicate effectively, and architectures that resist change rather than embrace it.

Contextual discovery—the systematic exploration and mapping of your business domain—isn't just a preliminary step in system design; it's the foundation upon which everything else is built. Without it, you're essentially constructing a skyscraper on quicksand.

"Most software projects don't fail because of the technology," observes Martin Fowler. "They fail because the people building the system don't understand the domain they're working in." This chapter will equip you with powerful techniques to avoid that fate.

## The Discovery Mindset: Anthropologists, Not Architects

Effective domain discovery requires a fundamental shift in mindset. You must temporarily suspend your solution-oriented thinking and approach the business domain with the curiosity of an anthropologist studying an unfamiliar culture.

This means:

1. **Embracing uncertainty**: Acknowledging that your initial understanding is incomplete and probably incorrect in significant ways
2. **Practicing deep listening**: Hearing not just the explicit statements but the implicit assumptions and mental models
3. **Looking for contradictions**: Paying special attention to inconsistencies in language and process, as these often reveal hidden complexity
4. **Suspending judgment**: Avoiding premature evaluation of practices as "inefficient" or "irrational" without understanding their context
5. **Seeking diverse perspectives**: Engaging with people across different roles, seniorities, and tenures

Monzo Bank exemplified this approach during their initial domain discovery. Rather than assuming they understood banking, their team spent weeks shadowing customer service representatives, interviewing customers about their financial lives, and mapping existing banking processes—before writing a single line of code. This anthropological approach revealed critical insights about how people actually think about money (very differently from how traditional banks are organised) that became central to their disruptive product design.

## Event Storming: Collaborative Domain Cartography

While several techniques exist for domain discovery, Event Storming has emerged as one of the most powerful. Developed by Alberto Brandolini, Event Storming brings together diverse stakeholders to create a temporal map of the domain using coloured sticky notes representing different elements.

The power of Event Storming lies in:

1. **Accessibility**: Using plain language and visual elements rather than technical notation
2. **Collaboration**: Bringing together business and technical people in the same conversation
3. **Focus on behaviour**: Emphasising what happens rather than static structures
4. **Scale**: Enabling the exploration of large, complex domains in a relatively short time

Here's how a basic Event Storming session unfolds:

1. **Preparation**: Gather a diverse group of domain experts and technical stakeholders. Create a large modelling space (typically a paper roll along a wall) and provide plenty of sticky notes in different colours.

2. **Domain Events**: Begin by asking participants to identify significant events that occur in the domain. These are captured on orange sticky notes and placed on the timeline in roughly chronological order.

3. **Commands and Actors**: For each event, identify the command that triggered it (blue sticky notes) and the actor who issued the command (yellow sticky notes).

4. **Policies and Read Models**: Identify policies that react to events (purple sticky notes) and the information models actors use to make decisions (green sticky notes).

5. **Aggregates and Bounded Contexts**: Group related events, commands, and actors into potential aggregates. Look for natural boundaries in the domain, which may indicate bounded contexts.

HMRC (Her Majesty's Revenue and Customs) used Event Storming extensively when redesigning their tax platform. By bringing together tax policy experts, enforcement specialists, technical architects, and user researchers, they uncovered critical domain nuances that had been obscured in their previous siloed approach. The resulting domain model revealed several distinct bounded contexts—tax calculation, payment processing, enforcement, etc.—with clear responsibilities and interfaces, which became the foundation for their microservices architecture.

## Domain Storytelling: Narratives as Knowledge Transfer

While Event Storming excels at mapping complex interactions, Domain Storytelling provides a complementary technique focused on specific workflows and user journeys. Developed by Stefan Hofer and Henning Schwentner, Domain Storytelling uses a simple pictographic language to document how people currently work in the domain.

The process involves:

1. **Gathering domain experts** who can tell stories about their work
2. **A facilitator** who visualises the story as it unfolds, using pictograms for actors, work objects, and activities
3. **Verification** of the story by the domain experts, correcting any misunderstandings
4. **Analysis** of the completed stories to identify patterns, edge cases, and potential bounded contexts

TransferWise (now Wise) employed Domain Storytelling to unpack the complexities of international money transfers. By collecting stories from compliance specialists, banking partners, and customer service representatives, they identified critical domain concepts like "mid-market rate," "conversion buffer," and "guaranteed rate" that weren't being consistently represented in their systems. These stories became the basis for a refined domain model and a shared language that bridged the gap between business and technology teams.

## Example Mapping: Distilling Business Rules

For more focused exploration of specific domain areas, Example Mapping provides a structured technique to discover and document business rules and edge cases. Introduced by Matt Wynne, Example Mapping uses a simple format of coloured cards:

- **Yellow**: User story or feature being explored
- **Blue**: Business rules that apply to the story
- **Green**: Examples that illustrate the rules
- **Red**: Questions that arise during the discussion

This technique excels at:

1. **Clarifying acceptance criteria** before development begins
2. **Uncovering hidden complexity** through concrete examples
3. **Identifying knowledge gaps** that require further investigation
4. **Creating a shared understanding** across business and technical perspectives

Ocado Technology applied Example Mapping when designing their complex warehouse automation system. For each warehouse operation (picking, packing, routing), they identified key business rules and illustrated them with concrete examples. This process uncovered numerous edge cases—like temperature-sensitive item handling and substitution rules—that would have caused significant rework if discovered only during implementation.

## Context Mapping: Charting Organisational Territories

As your domain discovery progresses, you'll likely identify multiple subdomains or bounded contexts within your overall business domain. Context Mapping, introduced by Eric Evans, provides a technique to document the relationships between these contexts.

A Context Map identifies:

1. **Bounded Contexts**: Distinct areas of the domain with their own language, models, and responsibilities
2. **Integration Patterns**: How contexts interact (e.g., Customer/Supplier, Conformist, Anticorruption Layer)
3. **Organisational Realities**: Team structures, existing systems, and external constraints
4. **Translation**: How concepts map between different contexts

ASOS, the online fashion retailer, created a comprehensive context map during their platform modernisation. This map revealed complex interdependencies between their Product Catalogue, Inventory Management, Order Processing, and Customer contexts. By explicitly documenting these relationships, they were able to design appropriate integration patterns that respected the distinct language and responsibilities of each context while enabling necessary data flow between them.

## Integrating with Wardley Mapping: The Evolution Dimension

While the techniques we've discussed so far help you understand your domain's current state, Wardley Mapping adds the critical dimension of evolution. As explored in Chapter 3, Wardley Maps help you visualise how components of your domain are evolving from genesis (novel) to commodity (standardised).

By combining domain discovery techniques with Wardley Mapping, you can:

1. **Identify which domain areas are rapidly evolving** versus stable
2. **Anticipate how your domain model might need to change** over time
3. **Make strategic decisions about where to invest** in custom solutions versus leveraging industry standards
4. **Prioritise which parts of the domain** to model in depth

UK Government Digital Service combined Event Storming with Wardley Mapping when redesigning citizen services. The Event Storming sessions revealed the domain's current structure, while Wardley Maps helped them identify which domain components (like identity verification) were evolving toward commodity solutions. This combined approach informed both their immediate technical architecture and their long-term strategic roadmap.

## Common Pitfalls in Domain Discovery

Even with these powerful techniques, several common pitfalls can derail effective domain discovery:

1. **The Solution Bias**: Jumping to technical solutions before fully understanding the domain

   _Remedy_: Explicitly separate discovery sessions from solution design sessions

2. **The Expert Assumption**: Believing that a single domain expert or architect can provide a complete view

   _Remedy_: Always involve multiple perspectives, especially from people who do the actual work

3. **The Static Fallacy**: Treating the domain as fixed and unchanging

   _Remedy_: Incorporate Wardley Mapping to understand evolutionary pressures

4. **The Perfect Model Trap**: Seeking a single, comprehensive model that represents the entire domain

   _Remedy_: Embrace bounded contexts and accept that different contexts will have different models

5. **The Technical Language Barrier**: Using technical or modelling terminology that excludes domain experts

   _Remedy_: Always use the language of the domain, not the language of software

Netflix avoided these pitfalls during their microservices transformation by treating domain discovery as an ongoing practice rather than a one-time event. They established regular "domain discovery days" where engineers and business stakeholders revisited their understanding of evolving domain areas, ensuring their architecture continuously aligned with business realities.

## Practicalities: Getting Started with Domain Discovery

Implementing effective domain discovery in your organisation doesn't require massive upfront investment. Here's a pragmatic approach to get started:

1. **Start small**: Choose a bounded, strategically important area of your business for initial discovery

2. **Gather the right people**: Include a diverse mix of domain experts, users, technical stakeholders, and a skilled facilitator

3. **Create the right environment**: Secure a physical space with ample wall space, or use collaborative digital tools designed for visual thinking

4. **Time-box effectively**: Initial Event Storming sessions work best as intensive 2-4 hour workshops, while longer-term discovery might span several weeks of part-time effort

5. **Capture and refine**: Document discoveries in accessible formats that both business and technical stakeholders can engage with

6. **Build feedback loops**: Use the models to drive development, then update them based on what you learn

Spotify exemplifies this iterative approach to domain discovery. They begin each significant initiative with a "design sprint" that incorporates domain discovery techniques. The resulting models directly inform their architecture and team boundaries, and they regularly revisit their domain understanding as they learn from implementation.

## The Business Value of Deep Domain Understanding

While some might view domain discovery as merely a technical prerequisite for good design, its business value extends far beyond that:

1. **Reduced delivery risk**: By uncovering complexity early, you avoid costly mid-implementation surprises

2. **Accelerated innovation**: A clear domain model makes it easier to identify opportunities for innovation and improved customer experience

3. **Enhanced organisational agility**: Well-mapped domain boundaries enable independent evolution of different business capabilities

4. **Improved knowledge transfer**: Explicit domain models reduce dependency on key individuals and accelerate onboarding

5. **Better business-technology alignment**: Shared models create a common language between business stakeholders and technical teams

Ping An, the Chinese insurance and financial services giant, attributes their successful digital transformation largely to rigorous domain discovery. By investing in comprehensive mapping of their complex financial domain, they were able to decompose their monolithic legacy systems into independent, business-aligned services. This domain-driven approach enabled them to launch new products 75% faster while reducing operational incidents by over 60%.

## Conclusion: Discovery as a Continuous Practice

The most sophisticated organisations don't treat domain discovery as a project phase but as a continuous practice. As your business evolves, your domain understanding must evolve with it. This requires:

1. **Regular revisiting** of domain models as you gain implementation experience
2. **Maintaining living documentation** that evolves along with your understanding
3. **Explicitly challenging assumptions** about the domain as market conditions change
4. **Creating feedback mechanisms** that incorporate learnings from users and operations

Amazon's "working backwards" approach exemplifies this continuous discovery mindset. Each new initiative begins with domain exploration, but they continuously refine their domain understanding based on customer feedback and operational metrics. This ensures their systems remain aligned with evolving business realities.

The journey toward adaptive systems begins with a deep understanding of your business domain. By mastering the techniques in this chapter and integrating them with the strategic perspective of Wardley Mapping and the organisational insights of Team Topologies, you create the foundation for systems that can evolve in harmony with your business needs.

Without this foundation, even the most sophisticated architecture or the most Agile delivery process will ultimately fail to deliver sustainable business value. Get the domain right, and everything else becomes possible.

## The Socratic Method Recap

**Student**: We already know our business domain well—we've been in this industry for years. Why should we invest time in formal domain discovery?

**Master**: Interesting. Let me ask you this: Can every member of your technical team explain your key business processes in the same way? And would that explanation match what your business stakeholders would say?

**Student**: Probably not. Different people have different perspectives.

**Master**: Precisely. And what happens when these different mental models collide during implementation?

**Student**: We get misunderstandings, rework, and features that don't quite meet business needs.

**Master**: And who in your organisation truly understands how all the different domains interact with each other? For instance, how exactly does your pricing domain influence your inventory domain?

**Student**: That's harder to answer. I'm not sure anyone has that complete picture.

**Master**: That's the value of explicit domain discovery—it transforms implicit, fragmented knowledge into a shared understanding that becomes the foundation for everything else. Without it, aren't you essentially building on quicksand?

**Student**: I see your point. But how do we convince stakeholders to invest in this?

**Master**: Rather than asking for a large up-front investment, what if you started with a focused domain discovery workshop for your next significant initiative? What specific area of your business would benefit most from this clarity?
