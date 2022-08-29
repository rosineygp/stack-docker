FROM {{ base_image }}:{{ tag_image }}

{% if package_manager == "apk" %}
RUN apk add --update --no-cache {{ packages }}
{% endif %}

{% if package_manager == "apt-get" %}
RUN apt-get update && apt-get install -y {{ packages }}
{% endif %}
