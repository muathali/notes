# Final Cut Pro

> Titles are for showing text, Generators are for creating backgrounds and filler content

## Resolution

Video is essentially a series of still images, and each frame has a horizontal and a vertical dimension in pixels. Common resolutions use abbreviations, including the following:

- **Ultra HD (UHD, aka 4K)**: 3840 x 2160
- **1080p**: 1920 x 1080
- **720p**: 1280 x 720

![resolution](./images/Screen%20Shot%202021-07-27%20at%203.58.40%20PM.png)

## Frame Rate

If it is at all possible, shoot in the same frame rate that you want to deliver. For a "cinematic" look, you'll want to shoot at 24 or 25 frames per second (fps), although 29.97 fps is widely used too.

Why these specific numbers?
A video image is updated a certain number of times per second, and that number is different for TV signals in different parts of the world for historical reasons related to electricity.

Here are some guidelines:

- In 110–120 V countries, such as the US, Canada, and elsewhere, 29.97 fps is used.
- In 240–250 V countries, such as most of Europe (including the UK), Australia, and New Zealand, 25 fps is used.
- In the international world of feature films and high-quality TV, 24 fps is the norm, although 23.98 fps is often used as it makes for easier conversion to US TV standards.

Does it matter which one you use if you're delivering online? Not much. But if you're delivering to TV or cinema, then it definitely matters, and you'll need to examine the delivery requirements carefully.

You might also have to deal with interlaced delivery (1080i) rather than progressive (1080p), but interlaced video today is only requested for TV broadcasts. Shoot and deliver in progressive formats, unless the client explicitly asks for interlaced delivery

It's also possible to record at moderately high frame rates, such as 50 or 60 fps, or even higher. While these frame rates do deliver smoother motion, most viewers find that videos shot in these modes look a little fake, unnatural, or cheap when played back at that speed, and so these higher frame rates are rarely seen outside of sports and gaming videos. Rather, these higher frame rates are more commonly used to give the option of slow motion, captured at a high speed, but played back at a slower speed

If you record at 60 fps, you can then slow it down on the timeline, showing every frame you shot for a speed of 42% on a 25 fps timeline or 50% on a 30 fps timeline. This is referred to as Automatic Speed in FCP, and it's very handy. But this is just an option — footage shot at a moderately high frame rate doesn't have to be slowed down. It's entirely possible to use this footage in real time instead by skipping frames on playback. Many shooters use these moderately high frame rates for B-roll (explained soon) to give more options during editing

Be aware that as you increase the frame rate, especially to higher numbers, the camera has to work harder, and you may have to compromise resolution as a result. Check your camera because there's often a distinction between "regular" frame rates, up to 60 fps, and "high-speed" frame rates, which can go much higher at a lower resolution, lower quality, and/or without audio. Whatever frame rate you shoot at, you should be consistent. While it's quite easy to incorporate slow-motion footage shot at any speed, your regular footage should all use the same frame rate — probably 24, 25, or 30 fps. Mixing similar frame rates can cause visible stutters (due to skipped or duplicated frames) and it's something to avoid if at all possible

## Shutter Speed

A separate but related issue is shutter speed, how many times per second an image is captured, which is expressed as a fraction of a second, such as 1/50 or 1/200. As a rule of thumb, to give your footage a natural motion blur, you should try to double your frame rate to determine the "ideal" shutter speed denominator:

- 1/48 or 1/50 for 24 fps
- 1/50 for 25 fps
- 1/60 for 30 fps

If you shoot at a significantly faster shutter speed, such as 1/100 or 1/200, the natural motion blur of 1/50 or 1/60 will be lost, and anything in motion will look a little "choppy" as a result. Conversely, if you shoot at a significantly slower speed, such as 1/25 or 1/30, everything in motion will look a little blurry.
It's important to note that this rule (known as the 180° shutter rule) does not apply to higher frame rates simply because any objects in motion will barely move between frames — there's hardly any blur to be had! If there's very little movement in the shot, there's not much blur in that either.

## Codecs

Most compressed videos today use a compression method (codec) called H.264, although H.265 (also known as HEVC) is becoming more popular. Support for HEVC (at the time of writing) is less mature; only recent Macs with a T2 chip can decode HEVC easily. Higher-end cameras might offer other options, such as ProRes, ProRes RAW, and Blackmagic RAW. While all of these formats do increase the quality, they take up significantly more space.
For example, a Panasonic GH5 records at a data rate of 100 Megabits per Second (Mbps) at 4K at 24/25/30 fps, or 150 Mbps for 4K at 50/60 fps, alongside many other options

The data rate for ProRes at the same resolutions and frame rates ranges from 470-589 Mbps, much, much higher than typical H.264 and HEVC codecs. These increased data rates require a much faster and larger recording device, typically an SSD rather than an SD card. You'll want to find a balance between quality and file size that suits your job's needs; read reviews, download files, and do the math to figure out how much space you'll need.
Lastly, it's very important to know that not all cameras compress video in the same way. H.264 from one camera can be easy to deal with, while footage from another camera stutters on playback. If it is at all possible, download some original footage from a camera you're planning on using to make sure it works well in your workflow. Expect new codecs and workflow changes in the future — standards do shift over time.

## Containers

Video data is encoded using a particular codec and is then stored in a container, usually a file with a .mp4 or .mov file extension. A container is not a codec, however; H.264 can be found inside many different types of containers, and a .mp4 file might contain video data in one of many different codecs. Still, you'll probably be fine; just look at the extension at the end of the filename to see which kind(s) your camera makes.
However, there are cameras out there that don't produce single contained video files at all. The AVCHD format, for example, spreads important data out on separate files across different subfolders, meaning you can't simply copy a file from an SD card and have a single video clip. Instead, the video data needs to be rewrapped inside a container format that FCP can use by importing directly from the SD card. Other cameras do contain their clips in single files (yay!), but they restart their file numbering on every card (boo!), leaving you to manage multiple files with identical names.
Where possible, I prefer to avoid AVCHD and other fussy container formats. A standalone video clip with a unique name using a standard codec is the gold standard, and plenty of cameras make files like this. If you're choosing the camera, don't bend over backward to support one that makes your life difficult.

## Optimized media (Pro Res 422)

Pro Res 422 is an Apple-designed "mezzanine" codec that is relatively large, high-quality, and easy to edit. While most compressed camera codecs are inter-frame, describing their image data in relation to previous frames or even frames coming up soon, ProRes is an intra-frame codec, like a series of still images that don't refer to one another. This is less efficient and takes up more space, but it's much simpler for your Mac to work with

ProRes 422 is actually just one codec in a family of others (including ProRes 422 Proxy, ProRes 422 LT, ProRes 422, ProRes 422 HQ, ProRes 4444, and ProRes 4444 XQ)

optimized footage uses the "vanilla" ProRes 422 codec. Regardless of the original camera, ProRes uses around the following amounts of data:

- ProRes 422 — 1080p, 24 fps: 117 Mbps or 14.6 MB/s
- ProRes 422 — UHD 4K, 24 fps: 471 Mbps or 58.9 MB/s

ProRes 422 data rates are far higher than most camera-original data rates, but that's probably OK for smaller jobs. Optimized media will be stored in the Library, along with the original media, and as the original media is not deleted, you will need plenty of space. If you have that space, there's just one extra step in your workflow:

1. Import the original media.
2. Transcode some or all of the media to optimized media (ProRes 422).
3. Edit.
4. Export.

For longer jobs, optimized media might require terabytes of space that you don't have, and you might need to use a different approach: proxies.

## Proxy media

While optimized files are a full-quality replacement for original media, proxy files are a medium-quality (and often lower-resolution) option that is only intended for use during the editing process. It'll look softer and possibly less pretty than you'd like, but that's fine while you're editing. Proxy media is quick to work with, and it doesn't take up nearly as much space as optimized media does. Previously, ProRes Proxy was the only way to go, at a data rate like this:

ProRes Proxy — 1080p, 24fps: 36 Mbps or 4.5 MB/s

From 10.4.9 onward, you can choose to use the small, efficient H.264 codec, at the resolution of your choice. If you want to save a ton of space, you can use a frame size as small as 12.5% of the original file. It's still fast, and the process is much the same, but these files will be much smaller than a full- or half-size ProRes Proxy:

- H.264 — 1080p, 24fps: 7.8 Mbps or 1 MB/s
- H.264 — 540p, 24fps: 3 Mbps or 0.375 MB/s

Note that if proxies have been created and you want to change their resolution or codec, you'll have to delete them (with File > Delete Generated Library Files or File > Delete Generated Clip Files) before recreating them at a different size.

Most kinds of original media can be optimized, but ProRes, HDV, and DV footage cannot. MP3 audio files are converted into uncompressed formats automatically on import, so you can't optimize them manually either.

## Viewing proxy media

If you create proxy files, you also have to choose to view them. You can choose to view Optimized/Original files exclusively, proxy files exclusively with Proxy Only, or use Proxy Preferred (new in 10.4.9) to show proxy if available, and the original or optimized file if the proxy isn't available or hasn't yet been created. That last option is what you want while you're editing with proxies, and when you're done with the edit and before you export, switch back to the original quality media.
To the workflow, then — if you can't work with the original media and an optimized version would be too big, this is the best way forward:

1. Import the original media.
2. Transcode the media into a proxy format.
3. In the Viewer's View menu, switch to viewing Proxy Preferred.
4. Edit with proxy media.
5. In the Viewer's View menu, switch back to viewing Optimized/Original.
6. Export with the optimized/original media.

Proxy workflows can save a lot of space, but if you view proxy media, that's what you'll export. Always remember to switch back to Optimized/Original before sharing — though you'll be warned if you don't.

## Skimming

Probably the first habit that most editors need to break when shifting to FCP is that of clicking. There's simply no need to click on a clip before playing it back, and in fact, it can cause issues if that click turns into an accidental drag and changes the current selection. Instead, *simply hover your cursor over a clip's filmstrip, just before a particular moment, then press the spacebar*

## Playback Shortcuts

Shortcut | Description
---------|----------
**Space** | Hover in the timeline, then press **Space** for play/pause
**L** | Plays forward
**K** | Pauses
**J** | Plays backwards
**↓ or apostrophe (')** | jumps to the first frame of the next clip
**↑ or semicolon (;)** | jumps to the first frame of the previous clip

Repeatedly press J or L to double the playback speed in that direction: 2x speed, 4x speed, 8x speed, and so on.
Hold K and then tap L to move a single frame forward.
Hold K and then tap J to move a single frame backward.
Hold K and then hold J or L to play in slow motion with slowed-down audio.

### The horizontal arrow keys are important too

Shortcut | Description
---------|----------
**→** | Moves forward one frame.
**←** | Moves back one frame
**⇧ →** | Moves forward 10 frames
**⇧ ←** | Moves back 10 frames
**⇧ ↓** | Selects the next clip
**⇧ ↑** | Selects the previous clip

All these keys also work with hovering, so you can hover to where you want to begin, then press J to play backward. If you click, rather than hover, you will also select the clip you clicked on

### Extended Short Cuts

To review a particular part of a clip, you can certainly hover or click just before a moment of interest, then simply play. But the following technique is often more useful:

- Activate Looping with View > Playback > Loop Playback (⌘L)
- Press ? to Play Around Edit

This is a great way to repeatedly see part of a clip as the Playhead jumps a few seconds back, plays through the selected point, and plays a few seconds forward before starting again. It's useful in an edit on the Timeline too

### Clips

Shortcut | Description
---------|----------
**I,O** | To select part of a clip
**F** | To mark as faviorate
**U** | To remove faviorate
**⌥ X** | To remove selection
**⌫** | Press the delete key (not forward delete) to mark selection as Rejected
**⌥M** | To create a Marker and edit its name

Pressing M alone is sufficient if you don't want to name a Marker. You could also press M twice to create it and then edit it, if you are careful not to move the mouse between the two keypresses

A Marker can be clicked on to show its name in the Skimmer Info (toggle with ⌃Y if you don't see it) above your cursor, and if Snapping is active, then you'll hit Markers easily while you skim. Snapping is a feature that will be used more during the editing process, but you can press N to toggle it on or off at any time

### Basic trimming with the Magnetic Timeline

Trimming, at a basic level, usually involves moving the edges of a clip to see more or less of it.

When you hover over the start or end of a clip, you'll see that the cursor changes to an icon that represents the start or end of a clip, with arrows on either side to indicate movement, and a filmstrip beneath.
That filmstrip points to the clip that's going to be adjusted, and also indicates that this is an operation that "ripples" — that is, it won't leave a gap. To many editors this is a Ripple trim or a Ripple edit, but here, we'll just call it a trim

When dragging edits, you may find that Snapping helps, but it can equally get in the way. If an edit point unhelpfully snaps to the Play-head (or anything else), just disable Snapping by pressing N during the operation

Trimming with the keyboard
Editing with the keyboard is effective, and if you're an experienced editor trying to nail those story beats, you'll like these:

1. Click near the start or end of a clip on the timeline to select the edit point.
2. Move that edit point one frame to the left with the comma key or one frame to the right with the period key. Use ⇧comma or ⇧period to move by 10 frames.

If you're trying to clean up an edit by trimming a few frames from a sequence of clips, you'll want to know a few more keys

Shortcut | Description
---------|----------
**[** | Selects the out point of the clip to the left of the Playhead.
**]** | Selects the in point of the clip to the right of the Playhead.

Trim Start and Trim End commands are a great way to make clips shorter, and they can be used while the video is paused, or while it's playing

- Press **⌥ [** to use Trim Start, moving the in point of the current clip to the current Playhead or Skimmer.
- Press **⌥ ]** to Trim End, moving the out point of the current clip to the current Playhead or Skimmer

### Extending edits

Occasionally, you might want to make a clip longer, rather than shorter, and there is a way to do that using the keyboard and the mouse together:

1. Select an edit point on a clip.
2. Skim over a point near that edit where you want the edit point to be.
3. Press **⇧ X** to perform an Extend Edit.

What did that do? Well, if you skimmed to a point inside the clip, it's just like using Trim Start or Trim End — it made the clip shorter. But if you skimmed to a point outside the clip, the clip will become longer; it's like you've grabbed that edit point and moved it. So why not just grab it with the mouse? Well, this operation can also be done entirely with the keyboard while the video plays, so if you prefer to edit by feel, it's a good way to work.

### Switching Tools

If you tap a key, you'll switch to that tool. But if you hold a key, you'll only switch to that tool temporarily, for as long as you hold it down

- Press **B** to switch to the Blade tool.
- Click on a clip to split it into two clips at that point:
- The new edit is indicated with a dashed line for now. It's called a through edit because the two frames around the edit are actually sequential. If you change your mind, through edits can be selected (with the Select tool) and deleted, healing the clip as if it was never bladed.

There's another way to blade that gives the same result, but without switching tools. As the video plays back, you can press **⌘B** to break up the current clip at the Playhead, and the strength of this approach is that you can blade a clip while it's playing. That's certainly handy from time to time, but Blade (either way) shouldn't be your first choice. If you want to make a clip shorter, Trim Start and Trim End are more efficient. If you want to delete part of a clip, it's not the best for that either

### Selecting part of a clip

It's much easier to delete part of a clip with this tool with the following steps:

1. - Press R for the Range Selection tool.
2. - Click on the clip where you want the edit to begin, then drag left or right and release where you want it to end, on the same clip or another clip

This process makes selecting in the Timeline just like selecting in the Browser. Just like the Browser, you don't need to use the mouse at all. If you'd prefer to use the mouse, you don't even need to switch tools, and the process is even simpler:

1. Skim to the start of the edit and **press I**
2. Skim to the end of the edit and **press O**

At this point, a handy shortcut could be /, to play just the selected region. If you've selected part of a single clip, you can press `⌥ \` to trim the selection to remove the unselected areas.

## Connections, Cutaways, and Storylines

A cutaway is the term for video placed above the main story to hide edits underneath

Removing the ums, ahs, and pauses leaves visible jump cuts: two sequential shots with almost, but not quite, the same content.

To hide the edits, an editor places a cutaway above the Primary Storyline, and while you still hear the words below, you don't see the jump cut.

How does the editor find the right clip to "cut away" to? Usually, they use B-roll that's related to the current topic. An edit has to feel justified, so you can't just put any old clip on top. This is why editors want relevant B-roll; if you don't have enough, you won't be able to cover all of the edits you want to.

Not all cutaways are B-roll, though. You might cut away to a reaction shot such as an interviewer nodding or a reverse angle of a character in a dramatic piece reacting to another. It could be a wider angle of the same scene, a close-up of an important detail, or something else. **Cutaways allow timing to be adjusted beneath them, and by shifting the audience's gaze, can help you to maintain an illusion of continuity**

As well as covering up an edit, cutaways can also be used above a continuous, unedited shot to break up a shot that's been on-screen for too long or to hide something. The defining factor of a cutaway is that it sits above the Primary Storyline rather than within it

you'll place clips above other clips simply when you want to cover something up or you want to stay flexible with regard to its position in time. You'll also use connected clips when you use keying (green screen) or picture-in-picture effects

### Understanding connections

Probably the biggest difference between a traditional editing timeline and the FCP Magnetic Timeline is the way in which clips sit above or below other clips. In a traditional editing application, a clip's timecode is the most important factor: clips sit at a point in time, and any relationship between two clips positioned above or below one another is merely implied. Such clips can move out of sync with each other if you're not careful.
Here in FCP, clips on the Primary Storyline form the spine around which everything else is built: clips above or below are always connected to a clip on the Primary Storyline, no matter how many clips there are in the stack. When a clip with connections is moved, the connected clips also move, and when a clip with connections is deleted, the connected clips are also deleted. Logically, this makes sense: a shot of a car should be connected to a person talking about that car. It's even clearer for sound effects: a sound effect of a car backfiring belongs to a specific time within a shot of a car. Music behaves a little differently though.

In the Viewer, you'll only see the clip that's highest in the stack at a point in time, and if the wrong clip is on top, you can drag clips directly up or down to change the stacking order. (**A quick tip: hold ⇧ as you move a clip up or down to avoid also moving it in time.**)

### Grouping connected clips in Storylines

If you place music or a longer voiceover in a Storyline, you can use the Range Selection tool to select anything you don't want, then press delete to close gaps automatically. Conversely, if you do want Gap clips in a Storyline (and you can make one with ⇧delete), they can be extended in time to increase the length of a pause.

### Controlling and overriding connections

First, if you want to connect a clip at a different point, hold `⌥ ⌘` and click on the connected clip. The connection will now be shifted to the clicked point in time, connecting to the clip on the Primary Storyline at that timecode. The same applies to Storylines, but you'll have to hold ⌥⌘ and click in the gray bar just above the clips instead
Moving connections like this lets you change which Primary Storyline clip "owns" a connected clip. As connected items are moved or deleted when a Primary Storyline clip is moved or deleted, this lets you decide which primary clips control those connected clips

If you don't want the connected clip to move:

- Reposition connected clips to a point preceding (not following) the clip you're about to delete. This isn't always possible.
- Use ⇧delete instead of delete to replace a clip with a Gap clip. The connected clips remain in the same spot with the same connection points:

There's one more solution that warrants deeper discussion:
Hold down the ` key (grave, on the same key as ~ or tilde) to temporarily override connections on primary clips you're rearranging or deleting.

When holding `, you'll see an additional icon appear on your cursor.
The "override connections" mode is an important toggle: any clips connected to the clip you're moving or deleting will stay where they are as if they weren't connected at all

## Three-point editing and more

You may not have considered it, but most edits are defined in terms of the source clip (which part of a clip you want to use) rather than the timeline (where do you want the clip to go). However, it's possible to prioritize the timeline instead, and this is sometimes called "three-point editing," because technically, at least three points are defined every time you add a clip. It's a traditional method, and here, you'll learn about how to mark part of the timeline to receive a clip and how to connect or overwrite a clip to that region

So far, we've added connected clips in a somewhat haphazard, less controlled way, by selecting a few seconds of a clip and then pressing Q. That means that the three points are the In (1) and Out (2) on a Browser clip, plus an In (3) point on the timeline.
But you can flip that "source clip dominance" around by explicitly placing two of those points on the timeline. To connect a new clip in a specific region, do the following:

1. In the Browser, skim over a clip you'd like to connect at a point you'd like to start from, and press I to mark an In point.
2. In the timeline, skim to a point where you want to add the connected clip, and press I to mark an In point.
3. Skim to where you want to end the connected clip.
4. Press O to mark an Out point:
5. Press Q to connect the selected clip:
If the source clip has enough media to fill the selected region of the timeline, a clip will be connected to just that region. It'll start from the In point you chose in the Browser, and run for the length you chose in the timeline, but the Out point in the Browser (chosen or implied) will be ignored. The Skimmer is also ignored, if present.

### Backtiming

From time to time, it can be more important what's at the end of a connected clip rather than the beginning, and there's a solution for that too. Instead of picking an In point in the Browser, press O to pick an Out point. And instead of pressing Q to connect, press Shift Q to perform a backtimed connect. This option places the Out point from the Browser clip at the Out point in the Timeline, then uses as much media before that point as the timeline region requires.

t's possible to Overwrite with two points on a source clip and a third on the timeline, but it's more common to put two on the timeline, as before:

1. In the Browser, skim over a clip you'd like to connect, at a point you'd like to start from, and press I to mark an In point (or O to mark an Out point).
2. On the timeline, skim to a point where you want to add the connected clip, and press I to mark an In point.
3. Skim to where you want to end the connected clip.
4. Press O to mark an Out point.
5. Press D to Overwrite the selected clip, or ⇧D to Overwrite with backtiming (from the Out point back)

What's different? This isn't a connection above the Primary Storyline but a replacement of the clips currently on the Primary Storyline. This is not an easily reversible operation, and any clips or regions within the selection will be entirely overwritten. Why do this? Well, I confess that I almost never do. If you want to use the Primary Storyline rather than connecting clips, then I can see the appeal, but I find connecting a clip above does what I want and lets any audio from the primary be heard.
One exception: you might want to Overwrite a clip into a connected Storyline. That's possible, but you'll have to select the Storyline (not a clip within the Storyline) before you press D or ⇧D. Again, that's not something I usually do, as I prefer to Replace — but that's coming up in the next chapter. Lastly, let's clarify copy and paste

## Copy and paste

Copy and paste are key operations in many applications, and while they're here too, connections can complicate matters just a little. If you copy a connected clip, it'll stay connected when you paste it, which makes sense. And if you copy a Primary Storyline clip, it'll paste to the Primary Storyline, performing an Insert operation and potentially breaking up a clip under the Skimmer. All of that makes sense.
If, however, you want to copy from the Primary Storyline and then paste as a connected clip, you'll need to use Edit > Paste as Connected Clip (Shift V) instead of a regular paste. There's no complementary operation to "paste as primary" but it's easy to do a regular paste and then drag it into the Primary Storyline if that's what you want.
