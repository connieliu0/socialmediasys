<script>
    import NodeConnections from './components/NodeConnections.svelte';
    import Cloud from './components/Cloud.svelte';
</script>

<main>
    <h2>
        craft your own social network
        </h2>
        <p style="color:white; filter: blur(0.5px);"><em>click on nodes to connect</em></p>
    <NodeConnections />
    <div class="body-text">
    <p>
        When I first got on Instagram in 2013, no one I really knew was on it. I posted a heavily filtered photo, tried to scroll through content with hashtags and then gave up. Then several years passed and suddenly Instagram had become an app where everyone was an influencer, everyone scrolled content made by people they didn't know, and everyone I knew was on it but few were really on it in the social way. 
    </p>
    <p>
        The design of social media is simple, within the tenets of web 2.0, every system has accounts, content, and the interactions between the two. However the changes on each design decision can lead to a very different experience. Take Threads and Twitter - both are extremely similar in design yet have different niches because the onboarding flow for Threads optimizes for sharing your social graph from your Instagram, which removes the anonymity many enjoy through Twitter. I wanted to see if I could figure out the system design of social media, and the path to take to design a network that would bring my most earnest self.
    </p>
    <h3>
        The Social Media Theory of Everything
    </h3>
    <h4>1. Network</h4>
    <p>
        A part of me feels like the death of social media isn’t exactly anyones fault but just the fact of growing up. When I first had social media in high school, rather than watching friendship from afar, it gave a texture to everyday friendship. To me, social media was how I memed with my friends in high school - an instagram account dedicated to the high school prompter, “grave-digging” on friend’s old facebook posts, captioned snaps of our friends, a facebook event page for working on our english assignment 24 hours before the deadline.
    </p>
    <p>
        But part of growing up is ultimately leaving the nest. Social media ultimately isn’t flexible for your twenties, when your identity and environment goes through rapid changes and shifts. People transiently pass in and out of your lives and there is usually no set environment. Because Instagram has replaced changing contact info, you end up with a mass amount of followers who you don’t know very well at all or people from your past [you likely will not ever see again](https://www.theatlantic.com/health/archive/2015/10/how-friendships-change-over-time-in-adulthood/411466/). It feels strange to post knowing people who don’t know your present context very well might interpret it differently.
       </p><p>
Perhaps the solution is to delete all your social media accounts when you’re 30 and start anew. There’s a phenomenon me and my friend termed as “millennial posting” in which you post whatever you want, whenever you want, usually shower thoughts overlaid on an image which stands in stark contrast to “genz posting" in which there is either little posting or a cryptic image once every few months. When you’re settled down and your social graph starts to become smaller and more consistent again, we can go back to our roots.
    </p>
    <h4>2. Persistence</h4>
    <p>
        Snapchat, if we disregard the actual purpose of it, was really revolutionary with the principle of ephemerality. The reality of life is everything changes and nothing is forever. If social media is who we are, there is something limiting about the chronological permanence of our posts. Our past selves contradict our present, it serves a reminder of times come and gone. Knowing what we post will disappear brings a clearer earnestness in the imperfections and irrelevance, but beauty, of the everyday.    </p>
    <p>
        <h4>3. Media</h4>
       <p>
        The pre-existing media can broken into several types - image, long text, short text, and video.  Image and video are more reflective of your outer world, whereas text represents messages from your inner world. I’m more likely to post how I’m feeling on Twitter than Instagram, because there isn’t really an image that can precisely capture what I’m feeling like words can. That being said, the more effort it takes to create the content - be it video or written piece, the more sincere it’s likely to be.    </p>
        <h4>Limit</h4>
        <p>When BeReal came out, it introduced a constraint - you can only post once per day, a feature that was counterintuitive to growth but encouraged sincerity. Many people wouldn’t post on time, they’d save their post for something more interesting. On Retro, you can only post photos from your week, encouraging a more immediate reflection to sharing. Beyond time or frequency, even limiting when you post to real life action, such as Strave (or even Venmo), begets a more authentic post than most platforms. I find that limits encourage quality, real-time sharing - but to do so and also feel a sense of connection only work in close, intimate networks.</p>
   <h4>Spread</h4>
   <p>Cultivating influencer culture relies on one core principle, how easy is it for us to become known? What Tiktok did differently was it became truly easy for anyone to reach who they wanted to. I’d disagree that influencing is a performance, since all performing comes from a root of self. We share to reach others because we want parts of ourselves that are hidden to be recognized. I create to be seen by those who understand that part of myself. </p>
    <h4>Other factors</h4>
    <p>There are other factors I didn’t include as core since I don’t think they affect the self we put out on social media as much. Direct messaging, chronological records, and the creator tools itself all amplify existing effects, but their inclusion or lack thereof don’t particularly change the person we become through social media.</p>
    <h3>The Theory of the Death of Social Media</h3>
    <p>
        When boiled down to its essence, social media is a simple concept whose power and difficulty lies in network effects. It’s easy to create a platform, but hard to get it to stick, which is why so many new ones have aggressive referral strategies (Lapse/Ditto I’m looking at you). If no one you know is on the platform, then it dies.     </p>
<p>It’s kind of crazy how getting early on a simple concept can lead to outsized effects on human history. It’s very difficult to destroy the platform capitalism that exists today and some might argue the ubiquity of usage is the basis for participating on the world’s stage. But what happens when the platform changes away from neutrality. When an algorithm profits off of aggression and antagonism - making it ever more difficult to escape from the doom loop.</p>
<p>No one is posting, everyone is posting, you’re in the spectacle whether you want to or not. There’s more content being created and consumed than ever, every time I look at my seat neighbor on a train they’re scrolling through their Reels. So what do we do when social media is dead; long live social media - but what is that exactly!</p>
<p>I’m not sure if I have the answer to replacing the forum for the world’s discourse, perhaps one day federated platforms will enter the mainstream and we can all own our own data. But for now, I have but simple dreams for social media - a flowering field where we can be our true selves - and like how we are forever changing, the form in which it takes changes too.</p>
<p>Read on Substack <a href="https://corny.substack.com/p/the-social-media-theory-of-everything">here</a></p>
</div>
</main>

<style>
    h2{
        filter: blur(1px);
    }
    h3,h4{
        color:blue;
    }
    main {
        width: 100%;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    p {
        z-index: 2;
        color: blue;
        text-align: left;
        margin-bottom:1em;
    }
    .body-text {
        width: 800px;
        margin: 0 auto;
        background-color: white;
        padding: 30px;
        filter: blur(0.6px);
        box-shadow: 0px 0px 25px 48px rgba(255,255,255,1);
        border-radius: 5rem;
        display: none;
        text-align: left;
        margin-bottom: 100px;
    }
    .body-text:has(p) {
        display: block;
    }
</style>