# timeline
A data set + website + React component for saying what happened when and putting time in perspective.

Not very related, but see also https://waitbutwhy.com/2013/08/putting-time-in-perspective.html .

What we have in here:

## data

{Human,computer}-readable timeline data in YAML, with useful attributes such as a good description, categories, importance etc. The need for selecting a reasonable subset for different zoom levels has been taken into account.

The description tries very hard to be correct and informative, especially for cosmological events. (Actually, I am much better at cosmology than at history...)

## React component

A self-contained React component for adding this timeline to your project. You may pass it the data from here, or your own. It supports a bunch of useful props that set what and how to show, and can transition smoothly (e.g. zoom out) when you change them.

## Website for exploring this

Will put a link here once it exists.

--------------------------------------------------------------------------

**PRs are very welcome!** Especially (but not only) for data.

I will use this in an awesome project that I'm not yet ready to announce. I wonder what you will use it for ;-)
