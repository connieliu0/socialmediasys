<script>
    import NodeConnections from './components/NodeConnections.svelte';
    import Cloud from './components/Cloud.svelte';
    import ExpandableText from './components/ExpandableText.svelte';

    let showBodyText = false;

    function handleCloudComplete() {
        showBodyText = true;
    }
</script>

<main>
    <div class="title-container">
        <h2>
            the social media theory of everything
        </h2>
        <p class="subtitle"><em>click on nodes to connect</em></p>
        <p class="mobile-message">view on web for the best experience</p>
    </div>
    <NodeConnections on:cloudComplete={handleCloudComplete} />
    <div class="body-text" class:visible={showBodyText}>
    <p>
        When I first got on Instagram in 2013, no one I really knew was on it. I posted a heavily filtered photo, tried to find content with hashtags and then gave up. Several years passed and suddenly Instagram had become an app where everyone was an influencer, everyone scrolled content made by people they didn’t know, and everyone I knew was on it but few were really on it in the social way.    </p>
    <img src="/firstpost.jpg" alt="graph" style="width: 300px;" />
    <p>
        The design of social media is simple, within the tenets of web 2.0, every system has accounts, content, and interactions between the two. However the changes on each design decision can lead to a very different experience. Take Threads and Twitter - both are extremely similar in design yet have different niches because the onboarding flow for Threads optimizes for sharing your social graph from your Instagram, which removes the anonymity many enjoy through Twitter. I wanted to see if I could figure out the system design of social media, and the path to take to design a network that would bring my most earnest self.
    </p>
    <h3>
        The Theory of the System
    </h3>
    <h4>1. Network - who sees this?</h4>
    <p>
     A part of me feels like the death of social media isn’t exactly anyones fault but just the fact of growing up. When I first had social media in high school, rather than watching friendship from afar, it gave a texture to everyday friendship. To me, social media was how I memed with my high school friends - an instagram account dedicated to the school prompter, <ExpandableText 
            mainText="grave-digging on friend's old facebook posts" 
            addendumText="this is where you would post a comment on someone's really old post (for example their birthday event) and then it would bring it back on the feed for everyone and we would all make jokes in the comments."
        />, captioned snaps of our friends sleeping in class, and my favorite - a facebook event page for working on our english assignment 24 hours before the deadline.
    </p>
    <img src="/hs_examples.jpg" alt="graph" />

    <p>
        But part of growing up is ultimately leaving the nest. Social media isn't flexible for your twenties, when your identity and surroundings go through rapid changes. People transiently pass in and out of your lives and there is usually no set environment. Because Instagram has replaced exchanging contact info, you end up with a mass amount of followers who you don't know very well at all or people from your past <a href="https://www.theatlantic.com/health/archive/2015/10/how-friendships-change-over-time-in-adulthood/411466/" target="_blank" rel="noopener noreferrer">you likely will not ever see again</a>. It feels strange to post honestly knowing people who don't know your present context very well might interpret it differently.
    </p><p>
        Perhaps the solution is to delete all your social media accounts when you're 30 and start anew. There's a phenomenon me and my friend termed as "millennial posting" in which you post whatever you want, whenever you want, usually shower thoughts overlaid on an image which stands in stark contrast to "genz posting" in which there is either little posting or a cryptic image once every few months. When you're settled down and your social graph starts to become smaller and more consistent again, we can go back to our roots.
    </p>
    <img src="/graph.png" alt="graph" />
    <h4>2. Persistence - how long will this last?</h4>
    <p>
        Snapchat, if we disregard the original purpose of it, was really revolutionary with the principle of ephemerality. The reality of life is everything changes and nothing is forever. If social media is who we are, there is something limiting about the chronological permanence of our posts. Our past selves contradict our present, it serves a reminder of times come and gone. Knowing what we post will disappear brings a clearer sharpness in the imperfections and irrelevance, but beauty, of the everyday.
        <p>
        <h4>3. Media - what is the content?</h4>
       <p>
        The pre-existing media that’s exchanged can broken into several types - image, long text, short text, and video. Image and video are more reflective of your outer world, whereas text represents messages from your inner world. I'm more likely to post how I'm feeling on Twitter than Instagram, because there isn't an image that can precisely capture what I'm feeling like words can. That being said, the more effort it takes to create the content - be it video or written piece, the more likely it's from the heart.
        <h4>4. Limit - what are the rules?
        </h4>
        <p>
            When BeReal came out, it introduced a constraint - you can only post once per day, a feature that was counterintuitive to growth but encouraged sincerity. Many people wouldn't post on time, they'd save their post for something more interesting. On Retro, you can only post photos from your week, encouraging a more immediate reflection to sharing. Beyond time or frequency, even limiting when you post to whether you’ve completed a real life action, such as Strava (or even <a href="https://www.theatlantic.com/technology/archive/2024/08/venmo-social-media/679665/" target="_blank" rel="noopener noreferrer">Venmo</a>), begets a more authentic post than most platforms. I find that 'limits' encourage quality, real-time sharing - but to do so and to also feel a sense of connection only works in close, intimate networks.
</p>
            <h4>5. Spread - will it reach who I want?
            </h4>
   <p>
    Cultivating influencer culture relies on one core principle, how easy is it for us to become known? What Tiktok did <a href="https://x.com/manasjsaloi/status/1880975536488677674" target="_blank" rel="noopener noreferrer">differently</a> was it became truly easy for anyone to reach their intended audience and so people would post whatever they wanted because it’d be seen. I'd disagree that influencing is a performance, since all performing comes from a root of self. We share to reach others because we want parts of ourselves that are hidden to be recognized. I create to be seen by those who understand that part of myself, in that way, perhaps I'm being more authentic than in any other form.
</p>
    <h4>Other factors</h4>
    <p>
        There are other factors I didn't include as core since I don't think they affect the self we put out on social media as much. Direct messaging, chronological records, and the creator tools itself all amplify existing effects, but their inclusion or lack thereof don't particularly change the person we become through social media.
</p>
        <h3>The Theory of the End of Social Media</h3>
    <p>
        When boiled down to its essence, social media is a <ExpandableText 
            mainText="simple concept" 
            addendumText="if you think about it all of these networks have the same nuts and bolts - the IG post format has not changed at its core in the last ten years besides adding music"
        />. It's easy to create a platform, but hard to get it to stick, which is why so many new ones have <ExpandableText mainText="aggressive referral strategies" addendumText="for example, one app wouldn't let me use it until five of my friends downloaded it"/>. If no one you know is on the platform, then it dies.
</p>
        <p>It's kind of crazy how getting early on a simple concept can lead to outsized effects on human history. It's very difficult to destroy the platform capitalism that exists today and some might argue the ubiquity of usage is the basis for 
            <a href="https://www.ystrickler.com/the-dark-forest-theory-of-the-internet/" target="_blank" rel="noopener noreferrer">participating</a> on the 
            <ExpandableText mainText="world" addendumText="further discussion on internet forestry https://www.wrecka.ge/against-the-dark-forest/"/>'s stage. But what happens when the platform <a href="https://www.npr.org/2024/10/22/nx-s1-5156184/elon-musk-trump-election-x-twitter" target="_blank" rel="noopener noreferrer">changes</a> away from <ExpandableText mainText="neutrality" addendumText="you can see this in the pre/post trump tiktok events https://www.dazeddigital.com/life-culture/article/66029/1/social-media-death-spiral-twitter-x-tiktok-instagram-elon-musk-mark-zuckerberg"/>?</p>
<p>No one is <a href="https://techcrunch.com/2024/12/23/instagram-tests-a-way-to-show-you-story-highlights-you-didnt-get-a-chance-to-see/" target="_blank" rel="noopener noreferrer">posting</a>, everyone is <a href="https://www.newyorker.com/culture/infinite-scroll/the-desperation-of-the-instagram-photo-dump?source=Paid_Soc_FBIG_CM_0_ASCAUD_GTM_0_NYR_US_Prospecting_C" target="_blank" rel="noopener noreferrer">posting</a>, you're in the spectacle whether you want to or not. There's more content being created and consumed than ever, every time I look at my seat neighbor on a train they're scrolling through their Reels. So what do we do when <a href="https://www.theatlantic.com/newsletters/archive/2022/12/instagram-facebook-friends-online/672394/" target="_blank" rel="noopener noreferrer">social media</a> is dead; long live social media - but what is that exactly!</p>
<p>I'm not sure if I have the answer to replacing the forum for the world's discourse, perhaps one day <a href="https://techcrunch.com/2024/02/22/bluesky-opens-up-federation-letting-anyone-run-their-own-server/" target="_blank" rel="noopener noreferrer">federated</a> platforms will enter the mainstream and we can all own our own data. But for now, I have but simple dreams for social media - a flowering field where we can be our true selves - and like how we are forever changing, the form in which it takes will change <ExpandableText mainText="too" addendumText="a topic I’ll explore for another time, but what if we all made different networks to be together? https://memory.elliott.computer/posts/social-media-is-just-another-website/"/>.</p>
<p>Thanks for reading! Read on Substack <a href="https://corny.substack.com/p/the-social-media-theory-of-everything" target="_blank" rel="noopener noreferrer">here</a> or go back to <a href="connie.surf" target="_blank" rel="noopener noreferrer">surfing</a>!</p>
    </div>
</main>

<style>
    h2{
        font-size: 1.25em;
        filter: blur(0.7px);
    }
    h3,h4{
        color:#0035ff;
        text-align:left;
    }
    main {
        width: 100%;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 0;
        margin: 0;
        box-sizing: border-box;
    }
    p {
        z-index: 2;
        color: #0035ff;
        text-align: left;
        margin-bottom:1em;
    }
    .body-text {
        width: 800px;
        margin: 0 auto;
        background-color: white;
        text-align: center;
        padding: 30px;
        filter: blur(0.6px);
        border-radius: 5rem;
        visibility: hidden;
        opacity: 0;
        transform: translateY(20px);
        transition: opacity 0.5s ease, transform 0.8s ease, visibility 0s linear 0.8s;
        box-sizing: border-box;
        box-shadow: 0 0 25px 24px #fff;
        margin-bottom:24px;
    }
    .body-text.visible {
        visibility: visible;
        opacity: 1;
        transform: translateY(0);
        transition: opacity 0.5s ease, transform 0.8s ease;
    }
 
    .title-container {
        width: 100%;
        text-align: center;
        margin-bottom: 1rem;
        padding: 0;
    }
    h2 {
        filter: blur(0.7px);
        margin: 0;
        width: 100%;
        padding: 0 1rem;
        box-sizing: border-box;
    }
    .subtitle, .mobile-message {
        color: white;
        opacity: 0.7;
        filter: blur(0.5px);
        margin: 0;
        width: 100%;
        text-align: center;
        padding: 0 1rem;
        box-sizing: border-box;
    }
    .mobile-message {
        display: none;
    }
    :global(body) {
        margin: 0;
        padding: 0;
        overflow-x: hidden;
    }
    img {
        width: 100%;
        height: auto;
        object-fit: contain;
        max-width: 100%;
    }
    @media (max-width: 768px) {
        .title-container {
            width: 100%;
            padding: 2rem 0rem 0rem 0rem;
        }
        h2 {
            font-size: 1em;
            padding: 0 1rem;
        }
        .body-text {
            width: 95vw;
            padding: 20px;
            margin: 0px 0px 48px 0px;
            border-radius: 2rem;
        }
        p {
            padding: 0;
            margin-bottom: 1em;
            box-sizing: border-box;
        }
        h3 {
            font-size: 1,2em;
        }
        h2 {
            font-size: 1em;
        }
        .mobile-message {
            display: block;
            font-size: 0.8em;
        }
        .subtitle{
            font-size: 0.8em;
        }
        main {
            padding: 0;
            width: 100vw;
            max-width: 100%;
        }
    }
</style>