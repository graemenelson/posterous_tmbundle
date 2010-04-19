# Simple Posterous TextMate Bundle

This is a very simple TextMate bundle that will convert a file from Markdown to HTML and post to your [Posterous](http://posterous.com) account through the [Posterous API](http://posterous.com/api).  
                                                                                 
**NOTE:** This bundle will not handle uploading media and images. And it's really new, and I haven't put it through it's paces yet.

## Requirements

The bundle requires rtomayko "RDiscount" gem.  To install run:

    gem install rdiscount
    
**NOTE:** you may need to sudo this command.

## Installing

To install the TextMate bundle, just copy/paste each line into your command line.

    mkdir -p ~/Library/Application\ Support/TextMate/Bundles
    cd ~/Library/Application\ Support/TextMate/Bundles
    git clone git@github.com:graemenelson/posterous_tmbundle.git 'Posterous.tmbundle'
    osascript -e 'tell app "TextMate" to reload bundles'      
    
In *Preferences > Advanced > Shell Variables* you can add the following variables for Posterous:

    TM_POSTEROUS_USERNAME
    TM_POSTEROUS_PASSWORD
    
If you don't add these variables you will be prompted for them at the time of submission.

## Usage

Once you have Markdown document ready to be submitted to your posterous account, just run *Bundles > Posterous > Push Markdown To Posterous*

### Title 

The *title* of the post will be taken from the name of the file.  For example:

    This is my post.markdown
    
Will become

    This is my post
    
Currently, you also get the option to change this title via a dialog popup at time of submission.  I will likely remove this, and just stick with name of the file.

### Tags

Currently a dialog is presented at the time of submission that allows you to enter tags (comma delimited).  I am looking into incorporating the tags into the document -- in order to get rid of the dialog input.

## Gotchas

* The posts aren't secure, I need to look at getting SSL working when posting to Posterous
* There is no error checking at this time, if you hit *Cancel* on the input dialogs, it will continue on
* I am not happy with all the dialog inputs, I will look into revising this.

