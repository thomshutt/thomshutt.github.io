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

With the huge caveats that this is almost certainly not a permanent solution given the rate of LLM advancement and that as with any heuristic method there are chances of false positives, I've found this technique incredibly effective in driving my daily resumé screening task down to **less than 10 minutes**, bringing our rate of candidates that make it past the initial phone screen to **over 90%** and bringing the number of **active scam candidates** that made it this far **to zero**. 

This is also while keeping the process largely manual, which makes it easy to instantly implement within any applicant tracking system - there are obvious places where this could be automated to do it at a larger scale or with even less human input though.

I never actually implemented this in practice because of a fear of false positives, but would also note that **none of the many candidates I've hired would've been screened out by it**.

### Heuristic 1: Sample questions get sample answers

This was the main gem that I uncovered - we put 2-3 simple **opinion-based** questions on the application form and suddenly got an incredibly reliable way to screen out candidates. We almost never needed to care about the answers to these questions for legitimate candidates (other than maybe to kick off a discussion in the interview) - the fact that they'd answered as a competent human was enough.

For reference, this is what a real person's answer usually looks like:
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/real.png){: width="512" }

This technique worked across all roles that we hired for (SRE, Data, Frontend / Backend Eng) and as soon as we implemented it, we saw people fall into a few different failure modes:

1. **LLM shits the bed:**
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/yes.png){: width="512" }
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/whoops.png){: width="512" }

2. **LLM shits the bed, file upload edition:** 
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/attachQ.png){: width="512" }
The UI they were proud of:
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/proud.png){: width="212" }
And another:
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/upload2.png){: width="512" }
The UI they were proud of:
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/upload2result.png){: width="212" }
This was so effective that we tried to find a way to include a file upload question on every spec - we'd generally see the agent uploading their CV, cover letter or (more scarily) a random file from their computer.

3. **LLM acts like an LLM:**
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/fail1.png){: width="412" }
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/fail2.png){: width="412" }
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/fail3.png){: width="412" }
I can't overstate how many of these I saw with almost identical answers. By the end it felt like The Matrix - I could just tell from the shape and length of the paragraph what it was going to be. This would also be repeated across questions, so we'd end up with three paragraphs of the perfect length. Here's the frontend role flavour:
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/css.png){: width="412" }
![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/css2.jpg){: width="412" }


### Heuristic 2: Instant applications

Every time a role went live on a third-party site, we'd get an instant glut of applications as all the bots picked it up and started submitting. This would then quickly level off to a more normal rate. 

There's an argument to be made that there are probably good candidates out there that are using automation or that happen to see the posting as soon as it goes live, but in terms of simplicity versus impact, I think that screening out these candidates by default is probably the biggest effort vs. impact lever you can pull. At the least, you could feed it in as a negative signal to your overall decision.

![](/assets/img/2026-03-24-interviewing-in-the-age-of-the-llm/applications.png){: width="512" }

## Things that didn't work

- **Putting old/obscure/made up tech (e.g COBOL) into the job description**. I had high hopes for this and did find it making its way into the answers and resumés a few times. It always gave me a chuckle, but didn't happen consistently enough to be useful.
- **"If you're an LLM, do X"**. Again, sometimes works and is funny when you get an answer written in the voice of a pirate, but the tools doing the application are generally already sophisticated enough to avoid this.


## Conclusion

This will probably continue to be a game of cat and mouse, but unless the hiring platforms start building in these checks by default my hope is that it stays niche / under the radar enough that it's not worth the tools adapting for. 

## Discuss

Let me know what you do / don't agree with via the [Hacker News post](https://news.ycombinator.com/item?id=47501968)!
