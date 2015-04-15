# Wildfish ratings

Add ratings to any model with a template tag.
You can have multiple ratings on one page (but only one rating per model instance)


## Installation

`pip install wildfish-ratings`

add `wildfish_ratings` to `INSTALLED_APPS`

    INSTALLED_APPS = (
        ...
        'wildfish_ratings'
    )

add the following to your urls.py:

    url(r'^ratings/', include('wildfish_ratings.urls', namespace='ratings', app_name='ratings')),


## Usage

Add the following javascript and stylesheet to you template
    
    <html>
    ...
    <link rel="stylesheet" href="{% static 'wildfish-ratings/css/wildfish-ratings.css' %}">
    <script type="text/javascript" src="{% static 'wildfish-ratings/js/dist/wildfish-ratings.js' %}"></script>
    ...
    </html>


To enable ratings for a model add the following tag in your template

    {% load ratings %}
    <html>
    ...
    {% ratings object %}
    ...
    </html>
    
    
## Settings

To prohibit users from altering their ratings set `WILDFISH_RATINGS_RERATE = False` in settings.py


## Template tags

The template tag takes three arguments:

*  `icon_height`: defaults to 32
*  `icon_width`: defaults to 32 
*  `star_count`: defaults to 5. This is the max rating (this means a value between 1 and 5)

To set a rating between 1 and 10 with an icon size of 16px: `{% ratings object 16 16 10 %}`


## Changing the star graphics

To change the star graphic, add a sprite sheet to `/static/wildfish-ratings/images/stars.png` with the states aligned horizontally.
