==========================
Django TemplateTags Extras
==========================

Custom template tags for Django>=1.6.1

Changelog
=========

0.1.0
-----

PENDING...

Notes
-----

PENDING...

Usage
-----

1. Run ``python setup.py install`` to install.

2. Modify your Django settings to use the needed application(s):
    2.1  current_url

3. Use the custom template tags as needed. Examples:
    3.1. For render the current url into page:

        {% load current_url_tags %}
        {% current_url %}

    3.2. For storing the current url in a context variable:

        {% load current_url_tags %}
        {% current_url as the_url %}

    3.3. For render the current url into page, for all available languages:

        {% load i18n %}
        {% load current_url_tags %}

        {% get_language_info_list for LANGUAGES as languages %}
        <ul>
            {% for language in languages %}
                <li {% if language.code == LANGUAGE_CODE %}class="active" {% endif %}>
                    {% language language.code %}
                        <a href="{% current_url %}">
                            {{ language.name_local }}
                        </a>
                    {% endlanguage %}
                </li>
            {% endfor %}
        </ul>
