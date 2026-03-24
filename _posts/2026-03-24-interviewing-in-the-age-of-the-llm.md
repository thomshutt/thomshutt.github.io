---
layout: post
title: "Interviewing in the age of the LLM - Screening"
date: 2026-03-24
tags: ["interviewing", "AI", "LLMs", "screening"]
og_image: /assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/header.jpg
header_image: /assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/header.jpg
---

## The game done changed

This post focuses on a low-effort / high-success technique that I used to screen candidates across multiple roles in a world where the time-cost of applying has effectively dropped to zero while also allowing candidates to generate a plausible application that's tailored to a given role.

## What does it look like to hire in 2026?

The bar is (and always has been) in hell in terms of the quality of the average applicant and their ability to:

- Produce a succinct resumé that captures their experience
- Do any kind of research on the company and role they're applying for
- Schedule an interview and turn up on time

but now with the new constraint that a lot of the techniques and signals I'd traditionally use for screening out low-quality candidates that weren't viable have now stopped being so effective. Candidates can now:

- Automatically pad their resumé with the desired skills for each role
- Type believable answers for any ancilliary questions on the job application
- Generate convincing live interview answers with AI assistance, at least for the initial screening

On top of that, you also have the exciting pitfalls of [North Korean Interview Farms](https://www.lbc.co.uk/article/north-korean-spy-ai-imposters-opinion-5HjdWmm_2/) and [r/overemployed enjoyers](https://www.theguardian.com/money/2026/jan/26/polygamous-working-why-are-people-secretly-doing-two-or-three-full-time-jobs-at-once) to try and avoid when hiring for remote roles.

Although these candidates will generally fall apart on a more in-depth technical stage, the further they get in the process (in-depth resumé review, HR phone screen, technical phone screen), the more of the company's time they eat up.

## What's the solution?

With the huge caveats that this is almost certainly not a permanent solution given the rate of LLM advancement and that as with any heuristic method there are chances of false positives, I've found this technique incredibly effective in driving my daily resumé screening task down to **less than 10 minutes** and bringing our rate of candidates that make it past the initial phone screen to **over 90%** and bringing the number of active scam candidates that made it this for **to zero**. 

This is also while keeping the process largely manual, which makes it easy to instantly implement within any applicant tracking system - there are obvious places where this could be automated to do it at a larger scale or with even less human input though.

### Heuristic 1: Instant applications

Every time a role went live on a third-party site, we'd get an instant glut of applications as all the bots picked it up and started submitting. This would then quickly level off to a more normal rate. 

There's an argument to be made that there are probably good candidates out there that are using automation or that happen to see the posting as soon as it goes live, but in terms of simplicity versus impact, I think that screening out these candidates by default is probably the biggest effort vs. impact lever you can pull. At the least, you could feed it in as a negative signal to your overall decision.

![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/applications.png){: width="512" }

I never actually implemented this in practice because of a fear of false positives, but would also note that **none of the many candidates I've hired would've been screened out by it**.

### Heuristic 2: Sample questions get sample answers

- File upload
- Sample questions

## Things that didn't work

- **Putting old/obscure/made up tech (e.g COBOL) into the job description**. I found this making its way into the answers and resumés a few times and it always gave me a chuckle, but it didn't happen consistently enough to be useful.
- 

## Conclusion