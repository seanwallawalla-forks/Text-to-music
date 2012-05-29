Text to Music
=============
by Andrew Faraday
contributors:
- Andrew Faraday
- Robin Gower

  A derivation of my very first ruby project, reading a string and converting it to control signals for puredata. The pure data patch recieves these via a TCP port and sends them to some short audio chains and the result is heard in sound.
  This has also been plugged-in to the twitter streaming API, to sonify tweets as they come in. A sort of literal twitter. 
  Watch out for rhyming and/or recurring words, you can actually hear that 'how now brown cow' rhymes. You can also get some drums sounds out of ascii characters: '_=_=___=_!_=__+='.

Requires:
  git 
  ruby
  rubygems 
  openssl-lib
  Pure Data Extended (from www.puredata.info)
Gems: (`bundle install`)
  tweetstream 
  highline

For manual import:
  Open ruby_interact.pd in puredata
  Open manual_input.rb in ruby (e.g. `ruby manual_input.rb`)
  Input a speed from 1 to 10
  Type some text and listen to the result.
  Repeat as required
  press `ctrl+c` to end the script

For twitter stream sonification:
  Open ruby_interact.pd in puredata
  `ruby twitter.rb`
  Input a twitter username and password when requested
  Watch the tweets contining 'fail' rolling in and being sonified
  To stop script press `ctrl+c` (you may have to hold it from there)
  Optionally:
    Modify the first few lines of twitter.rb to remove the need to type a username or to change the default search
    use arguments to change the searched for terms (e.g. ruby twitter.rb win or ruby twitter.rb lemmy bieber)

Likely errors:
  `initialize': Connection refused - connect(2) (Errno::ECONNREFUSED) - means that ruby_interact.pd is not open (it opens a TCP port to listen to the Character class)

Future intent:
 Connect to Pidgin or IRC, musical chat client. 
