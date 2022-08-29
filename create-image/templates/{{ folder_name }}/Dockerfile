FROM {{ base_image }}:{{ tag_image }}

{% if package_manager == "apk" %}
RUN apk add --update --no-cache {{ packages }}
{% endif %}
{% if package_manager == "apt-get" %}
RUN apt-get update && apt-get install -y {{ packages }}
{% endif %}
{% if package_manager == "yum" %}
RUN yum install -y {{ packages }}
{% endif %}
{% if code_package_manager == "pip" %}
RUN pip install {{ code_packages }}
{% endif %}
{% if code_package_manager == "npm" %}
RUN npm install -g {{ packages }}
{% endif %}