---
layout: default
---

<div class="_fragment-autofilm-banner">
    <div class="content">
        <div class="container text-center">
            <h1 class="text-shadow animated fadeInDown text-nowrap"><span class="text-hide">3M</span><img width="100" src="{{ site.baseurl }}/assets/img/3M.png" /><br class="d-md-none"/> {{page.main_title}}</h1>
        </div>
    </div>
</div>

{% for product in page.products %}
    <div class="section-light">
        <div class="container">
            <h2 class="text-center mx-auto">{{product.title}}</h2>
            <div class="row pt-2">
                <div class="col-12 col-md-6">
                    <img class="box-shadow img-fluid" src="{{site.url}}/assets/img/{{product.image}}">
                    <div class="mt-2 text-center">
                        {% if product.show_contact == true %}
                            <h3>Want to know more?</h3>
                            {% include contact.html %}
                        {% endif %}
                    </div>
                </div>
                <div class="col-12 col-md-6">
                    <h3>Details:</h3>
                    {% if product.content_path != null %}
                        {%- capture content -%}{% include {{ product.content_path }} %}{%- endcapture -%}
                        <div class="api-doc api-off api-definition" id="debugging">{{ content | markdownify }}</div>
                    {% endif %}
                </div>
            </div>
        </div>
    </div>
{% endfor %}

