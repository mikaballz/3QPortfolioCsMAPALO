# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.

-> I think the main difference between default static positioning and relative positioning is how the element can be moved. With static positioning, the element just stays in the normal flow of the page. You can’t really adjust it using top, left, bottom, or right, aka, it just follows the layout automatically. With relative positioning, the element still starts in its normal position, but now you can move it using top, left, etc. The important thing is that it moves relative to where it originally was, not from the corner of the page. So instead of being “linear positioning,” it’s more like you’re shifting the element from its original spot without affecting the rest of the layout too much.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?

-> I think it’s because the footer is set to fixed positioning. This means that even if there are other elements on the page, the footer won’t move or be affected by them. It stays in the same position on the screen no matter what. So when you scroll up or down, the footer doesn’t move, it just stays visible the whole time. Other elements might pass behind it, but they don’t push it away or change its position. This is different from relative positioning, where the element still moves along with the page when you scroll because it’s part of the normal document flow.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

-> From my observations, I didn't really see any obvious differences between the two AT FIRST. Even when values are interchanged and replaced, it still holds the sample positioning right beside one of the other elements. But then when you scroll down, you'll notice that the position fixed does not move, it stays FIXED in place, while as the absolute moves with the page as you scroll.


### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

-> When I swapped the value, the opposite happens! I think the z-index just implies the layering and which element goes on top of the other. So if the z-index is smaller than the other z-index, then it is at the bottom layer, while as the larger z-index value goes on top and overlays it. 

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    -> When I changed .content to position: relative, it still stayed in its normal place in the layout, but I could move it slightly using top and left. It still moved together with the page when I scrolled, so it felt like part of the normal flow. But when I changed it to position: fixed, it became very different. The content stayed in one place on the screen and didn’t move at all when I scrolled. It kind of looked like it was floating above everything else. It also ignored the normal layout, so other elements didn’t affect its position anymore.
    * What do you observe on about the effect of z-index on .notice and .content boxes?
    -> From what I observed, the z-index controls which element appears on top when they overlap. The element with the higher z-index will be placed in front, while the lower one goes behind. So when .notice has a higher z-index than .content, it appears on top of it. But when I switch the values, .content covers the .notice instead. I also noticed that z-index only works properly when the elements have a position (like absolute, relative, or fixed). Without positioning, the z-index doesn’t really do anything.

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 
    1. Static
    - Static is the default positioning, where elements just follow the normal layout of the page and can’t be adjusted using top, left, etc.
    2. Relative
    - Keeps the element in the normal flow, but allows you to move it slightly from its original position using top, left, and so on.
    3. Absolute
    - Removes the element from the normal flow and positions it based on its nearest positioned parent (or the page if there is none).
    4. Fixed
    - Also removed from the normal flow, but it stays fixed on the screen even when you scroll, unlike absolute which moves with the page.

    b. How does absolute positioning depend on its parent element?
    -> Absolute positioning depends on the nearest parent that has a position (like relative, absolute, or fixed). If the parent has a position, the element will be placed relative to that parent. But if none of the parent elements have a position set, then the absolute element will position itself relative to the entire page (viewport) instead.


    c. How do you differentiate sticky from fixed (you can research on sticky)?
    -> Sticky is kind of a mix of relative and fixed. At first, it behaves like a normal element and scrolls with the page. But once it reaches a certain point (like top: 0), it “sticks” and stays in place while scrolling. Fixed, on the other hand, is always fixed in one position from the start and does not move at all when you scroll.

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
    ->I would use fixed positioning for important things like a registration button so it stays visible even when users scroll. I could use absolute positioning to place labels or highlights on specific parts of the page, like putting a “New” or “Important” tag on event announcements. Sticky positioning would be useful for headers or navigation bars so they stay at the top while scrolling through event details. Lastly, I could use relative positioning for small adjustments, like aligning text or images properly without breaking the layout.
