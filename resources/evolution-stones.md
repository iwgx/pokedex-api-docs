# Evolution Stones

{% api-method method="get" host="https://pokeapi.glitch.me" path="/v1/evolution-stone" %}
{% api-method-summary %}
Evolution Stone Names
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns an array of Pokémon Evolution Stone names discovered in the Pokémon World.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="User-Agent" type="string" required=false %}
The User-Agent of your application
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Evolution stone names successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
[
    "Fire Stone",
    "Water Stone",
    "Thunder Stone",
    "Leaf Stone",
    "Moon Stone",
    "Sun Stone",
    "Shiny Stone",
    "Dusk Stone",
    "Dawn Stone",
    "Ice Stone"
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Example Request

```bash
curl -i -X GET \
  -H "User-Agent: BastionDiscordBot (https://bastionbot.org, v6.16.1po)" \
  https://pokeapi.glitch.me/v1/evolution-stone
```

{% api-method method="get" host="https://pokeapi.glitch.me" path="/v1/evolution-stone/:slug" %}
{% api-method-summary %}
Evolution Stone
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns a Evolution Stone object containing the details about the evolution stone.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="slug" type="string" required=true %}
The string used to identify this evolution stone
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="User-Agent" type="string" required=false %}
The User-Agent of your application
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Evolution stone successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Dusk Stone",
    "aka": "Darkness Stone",
    "slug": "dusk",
    "effects": [
        "Causes Murkrow to evolve into Honchkrow.",
        "Causes Misdreavus to evolve into Mismagius.",
        "Causes Lampent to evolve into Chandelure.",
        "Causes Doublade to evolve into Aegislash."
    ],
    "sprite": "https://pokeres.bastionbot.org/images/evolution-stones/dusk-stone.png"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "error": 404,
  "message": "Oh snap! No Pokémon has been discovered in this region. You should head home: https://pokedevs.bastionbot.org"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Evolution Stone Structure

| Field | Type | Description |
| :--- | :--- | :--- |
| name | string | The name of evolution stone |
| aka | string | The alternate name of the evolution stone |
| slug | string | The string used to identify this evolution stone |
| effects | array of strings | A list of the effects of using the evolution stone on a Pokémon |
| sprite | string | The URL of an image of the evolution stone |

#### Example Request

```bash
curl -i -X GET -H \
  "User-Agent: BastionDiscordBot (https://bastionbot.oorg, v6.16.1)" \
  https://pokeapi.glitch.me/v1/evolution-stone/dusk
```



