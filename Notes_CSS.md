
**************************************************************************************
Notes on CSS - Cascading Style Sheet
**************************************************************************************

--------------------------------------------------------------------------------------
 History of CSS
--------------------------------------------------------------------------------------

CSS was first proposed by Håkon Wium Lie on October 10, 1994. At the time, Lie was working with Tim Berners-Lee at CERN.Several other style sheet languages for the web were proposed around the same time, and discussions on public mailing lists and inside World Wide Web Consortium resulted in the first W3C CSS Recommendation (CSS1) being released in 1996. 

In particular, a proposal by Bert Bos was influential; he became co-author of CSS1, and is regarded as co-creator of CSS

Development of HTML, CSS, and the DOM had all been taking place in one group, the HTML Editorial Review Board (ERB). Early in 1997, the ERB was split into three working groups: HTML Working group, chaired by Dan Connolly of W3C; DOM Working group, chaired by Lauren Wood of SoftQuad; and CSS Working group, chaired by Chris Lilley of W3C.

CSS Working group all Standards Draft are given in the link below

https://www.w3.org/TR/#tr_Cascading_Style_Sheets__CSS__Working_Group


--------------------------------------------------------------------------------------
 Versions of CSS
--------------------------------------------------------------------------------------

CSS 1

The first CSS specification to become an official W3C Recommendation is CSS level 1, published on December 17, 1996. Håkon Wium Lie and Bert Bos are credited as the original developers. Among its capabilities are support for

    Font properties such as typeface and emphasis
    Color of text, backgrounds, and other elements
    Text attributes such as spacing between words, letters, and lines of text
    Alignment of text, images, tables and other elements
    Margin, border, padding, and positioning for most elements
    Unique identification and generic classification of groups of attributes

The W3C no longer maintains the CSS 1 Recommendation.


CSS 2

CSS level 2 specification was developed by the W3C and published as a recommendation in May 1998. A superset of CSS 1, CSS 2 includes a number of new capabilities like absolute, relative, and fixed positioning of elements and z-index, the concept of media types, support for aural style sheets (which were later replaced by the CSS 3 speech modules) and bidirectional text, and new font properties such as shadows.

The W3C no longer maintains the CSS 2 recommendation.


CSS 2.1

CSS level 2 revision 1, often referred to as "CSS 2.1", fixes errors in CSS 2, removes poorly supported or not fully interoperable features and adds already implemented browser extensions to the specification. To comply with the W3C Process for standardizing technical specifications, CSS 2.1 went back and forth between Working Draft status and Candidate Recommendation status for many years. CSS 2.1 first became a Candidate Recommendation on February 25, 2004, but it was reverted to a Working Draft on June 13, 2005 for further review. It returned to Candidate Recommendation on 19 July 2007 and then updated twice in 2009. However, because changes and clarifications were made, it again went back to Last Call Working Draft on 7 December 2010.

CSS 2.1 went to Proposed Recommendation on 12 April 2011. After being reviewed by the W3C Advisory Committee, it was finally published as a W3C Recommendation on 7 June 2011.

CSS 2.1 was planned as the first and final revision of level 2—but low priority work on CSS 2.2 began in 2015.


CSS 3

Unlike CSS 2, which is a large single specification defining various features, CSS 3 is divided into several separate documents called "modules". Each module adds new capabilities or extends features defined in CSS 2, preserving backward compatibility. Work on CSS level 3 started around the time of publication of the original CSS 2 recommendation. The earliest CSS 3 drafts were published in June 1999.

Due to the modularization, different modules have different stability and statuses.


CSS 4

There is no single, integrated CSS4 specification, because it is split into separate "level 4" modules.

Because CSS3 split the CSS language's definition into modules, the modules have been allowed to level independently. Most modules are level 3—they build on things from CSS 2.1. A few level-4 modules exist (such as Image Values, Backgrounds & Borders, or Selectors), which build on the functionality of a preceding level-3 module. Other modules defining entirely new functionality, such as Flexbox, have been designated as "level 1".

The CSS Working Group sometimes publishes "Snapshots", a collection of whole modules and parts of other drafts that are considered stable, interoperably implemented and hence ready to use. So far, five such "best current practices" documents have been published as Notes, in 2007, 2010, 2015, 2017, and 2018.

--------------------------------------------------------------------------------------
 Why CSS is called Cascading Style Sheets
--------------------------------------------------------------------------------------

In a page multiple sheets can be applied, and hence multiple rules can apply to same element. CSS applies all these rules in a cascading manner, in a hirarchical order , so more specific rule wins

The rule used is chosen by cascading down from the more general declarations to the specific rule required. The most specific declaration is chosen.

Priority	                CSS source type	Description

1	Importance	            The "!important" annotation overwrites the previous priority types
2	Inline	                A style applied to an HTML element via HTML "style" attribute
3	Media Type	            A property definition applies to all media types, unless a media specific CSS is defined
4	User defined	        Most browsers have the accessibility feature: a user defined CSS
5	Selector specificity	A specific contextual selector (#heading p) overwrites generic definition
6	Rule order	            Last rule declaration has a higher priority
7	Parent inheritance	    If a property is not specified, it is inherited from a parent element
8	CSS property definition in HTML document	CSS rule or CSS inline style overwrites a default browser value
9	Browser default	The lowest priority: browser default value is determined by W3C initial value specifications


The CSS Cascade is the algorithm by which the browser decides which CSS styles to apply to an element — a lot of people like to think of this as the style that “wins”.

Here are the attributes that the CSS Cascade algorithm checks, listed in order from highest weight to least weight.

    Origin & Importance
    Selector Specificity
    Order of Appearance
    Initial & Inherited Properties (default values)

Origin & Importance

    The cascade algorithm considers the combination of these 2 attributes when figuring out which declaration wins. Each combination is given a weight (similar to the way parts of a CSS declaration are weighted), and the declaration with the highest weight wins. Here are the various combinations of origin & importance that the browser considers, listed in order from highest weight to least weight.

        User-Agent & !important
        User & !important
        Author & !important
        CSS Animations, @keyframes (This is the only exception, it is still originating from the author, but as animations are temporary/fleeting the browser weights them slightly higher than normal author rules)
        Author, normal weight
        User, normal weight
        User agent, normal weight

    When the browser comes up against 2 (or more) conflicting CSS declarations and one wins at the origin & importance level, the CSS cascade resolves to that rule. No questions asked. Game over.

    However, if the conflicting declarations have the same level of importance/origin, the cascade moves on to consider selector specificity.

Selector Specificity

    The second weight in the CSS cascade is selector specificity. In this tier, the browser looks at the selectors used in the CSS declaration.

    As a front-end developer, you only have control over the “author” origin stylesheets on your websites — you can’t do much to change the origin of a rule. However, if you’re staying away from using !important in your code, you’ll find that you have a lot of control over the cascade at the specificity tier.

    Similar to the way that the combinations of origin & importance each have their own weight, different types of CSS selectors are assigned priority. When evaluating specificity, the number of selectors and their priority are considered. CSS selectors can belong to one of the following weighted tiers.

    Inline styles (anything inside a style tag)
    ID selectors
    Classes / pseudo-selectors
    Type selectors (for example, h1) & pseudo-elements (::before)

Source order

    The last main tier of the CSS cascade algorithm is resolution by source order. When two selectors have the same specificity, the declaration that comes last in the source code wins.

    Since CSS considers source order in the cascade, the order in which you load your stylesheets actually matters. If you’ve got 2 stylesheets linked in the head of your HTML document, the second stylesheet will override rules in the first stylesheet. This is also the reason that if you’re using a CSS reset or a CSS framework, you’ll want to load that before your custom styles.

Initial & inherited properties

    While initial & inherited values aren’t truly part of the CSS cascade, they do determine what happens if there are no CSS declarations targeting the element. In this way, they determine default values for an element.

    Inherited properties will trickle down from parent elements to child elements. For example, the font-family & color properties are inherited. This behavior is what most people think of when they see the word “cascade” because styles will trickle down to their children.

https://blog.logrocket.com/how-css-works-understanding-the-cascade-d181cd89a4d8/
