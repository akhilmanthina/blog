+++
title = "What if I made blogging needlessly complicated?"
date = 2025-07-26
[taxonomies]
tags = ["Blog Development"]
+++

## Inspiration

Making a blog was a concept so far removed from my wheelhouse. Writing just never flowed out of me naturally, rather it was something that needed to be reluctantly strained in pursuit of a grade. For each essay my teachers forced me into writing, I'd outdo myself with how closely I could tiptoe the deadline (11:59:58 PM record by the way). If procrastination was the feeling I associated with writing, why the hell would I do it voluntarily?

And yet, for all my love of reading the words of others, I'd never thought to contribute my own. That was until I realized why I had been losing my sense of fulfillment- I fell prey to consumption. There were the common perpetrators: YouTube, video games, and short-form content, but even reading, while notably healthier, falls under the umbrella. I used to make some sort of project every weekend as a kid, and I don't think I concerned myself much on whether they succeeded or failed. My attic is still scattered with boxes of half soldered perf boards, modded nerf guns, and foam board RC planes. Point being, I was building something, unabashed by its "meaningfulness". Creativity ushered meaning and satisfaction. 

So this whole thing is sort of an experiment to see whether I'll start living better with the pretense of a blog. Maybe I'll go, "Well damn I have nothing to write about... maybe I should make something cool, or do something new- for content of course". I'm now looking at writing as just another creative outlet. I don't need to produce a perfect essay, there's no rubric for this. I can just broadcast my mind, and in doing so, derive meaning. Mentally reframing the drudgery of writing into a form of making, little different from my hobbies of old, shifted my view and gave me the motivation to make this happen. There's also the altruistic aspect of giving back to the internet, from which I have learned so much. Perhaps one day, someone will come looking for a solution for an esoteric issue, stumbling upon their answer within this site. I just need to put whatever I can out there.

However [KISS](https://en.wikipedia.org/wiki/KISS_principle) is antithetical to fun, and fun is very *thetical* to getting anything done. Using Blogspot (damn they're still around!?) wouldn't do. At the very least, I knew I needed to make my own website (I actually tried this once-  [🥀🪦](https://github.com/akhilmanthina/portfolio)), and I knew I'd want it to be something engaging to maintain.  I had also encountered this site across devops forums - [The Cloud Resume Challenge](https://cloudresumechallenge.dev) - which sparked another, similarly brief, stroke of inspiration that whatever I deploy should be done so in a convoluted manner, all in service of learning.

It wasn't until I found this [video](https://www.youtube.com/watch?v=3isQI0nXQRE), credit to Network Chuck, that I knew the direction I wanted to take all this. Of *course* I needed to make a pipeline to blog. The idea was simple- write markdown, convert it with a Static Site Generator, and have it automatically pick up and deploy new pages I write. The over-engineering was reminiscent of the [opening scene](https://www.youtube.com/watch?v=3isQI0nXQRE) in Back to the Future, where we see Doc Brown's Rube Goldberg machine make toast and feed Einstein. My twist is to run the site off of a Raspberry Pi cluster- a past impulse purchase which I may well put to use. This also gives me an opportunity to sharpen SysAdmin and Kubernetes skills, and maybe I can run some other stuff of the cluster down the line. 

There is some practicality to be had with this approach. All the content is stored in simple markdown, with no reliance on a platform which may or may not exist in the future. This also lends itself to "easy" creation of new posts, simply via a markdown editor of choice. And perhaps most importantly, no Javascript. Regardless, it's time to finally put it together.

Here's the plan: 
1. **Generate the site** using [Zola](https://www.getzola.org), a static site generator from markdown content
2. **Deploy the site ASAP**. Just use some cloud provider (lest this project be trapped purgatory)
3. **Containerize the site** by creating a [Docker](https://docs.docker.com/get-started/docker-overview/) container running [Apache](https://httpd.apache.org)
4. **Run the site from a Raspberry Pi cluster**. Document the process of configuring the cluster in a separate post
5. **Commit the site** to Github and setup CI/CD- changes pushed should reflect in the live site

So, here begins my project- a little window into my head. Soon to be served by a quartet of silicon desserts in an attic. Source code stored publicly on Microsoft's servers (which already knew everything about me anyway). I'll be updating this page periodically as the infrastructure for this site evolves, but that's it for now.

## Progress

Step 1 obviously took longer than expected, as I brilliantly decided to not [RTFM](https://en.wikipedia.org/wiki/RTFM) for Zola, overcomplicating the process and bashing my head at compilation errors. Choosing a template was also a trickier undertaking than I had expected, as Zola is a less popular SSG compared to tools such as Jekyll or Hugo, there were fewer options in general. Eventually, I found [Duckling](https://duckling.aparoksha.dev) which itself was a more minimalist fork fo
