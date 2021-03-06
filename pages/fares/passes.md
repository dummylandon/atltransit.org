---
layout: page
title: Discounts & passes
id: passes
order: 3
category: 'fares'
permalink: '/fares/passes/'
tagline: Buy in bulk and reap the rewards. Also, find info on discounts for seniors, youth, and more.
sections: ["Regional fare pass", "Breeze Card passes", "Individual agency fare products"]
image: "/build/images/breeze_multi_agency.jpeg"
---

* toc goes here
{:toc class="list-inline anchor toc text-center col-sm-12"}

## Regional fare pass

Currently, a single regional fare pass **does not exist** for the Atlanta region. To receive bulk or monthly discounts you must buy a pass for a single transit agency.


## Breeze Card passes

<div class="col-sm-6 col-xs-12 pull-right">
	<img class="img-responsive center-block" style="max-height: 285px" src="/build/images/breeze_shadow.png">
</div>

Most discounts and passes for each individual transit agency are available on your Breeze Card.

<p class="text-center bottom-buffer"><a class="btn btn-lg btn-primary top-buffer" href="http://breezecard.com/">Visit breezecard.com <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a></p>

Here's a complete listing of Breeze Card fare products:

<div class="row">
	<div class="col-sm-6">
	{% for agency in site.data.fares %}
		<div class="panel-group" role="tablist">
		{% for product in agency.passes %}
			{% if forloop.first %}
			<div class="panel panel-default">
				<a role="button" data-toggle="collapse" href="#collapseListGroup{{ agency.id }}" aria-expanded="false" aria-controls="collapseListGroup{{ agency.id }}">	
					<div class="panel-heading" role="tab" id="collapseListGroupHeading{{ agency.id }}">
						<h3 class="panel-title">
							
								{{ agency.name }}
							
						</h3>
					</div>
				</a>
				<div id="collapseListGroup{{ agency.id }}" class="panel-collapse collapse" role="tabpanel" aria-labelledby="collapseListGroupHeading{{ agency.id }}" aria-expanded="false">
					<ul class="list-group">
			{% else %}
				<li class="list-group-item">{{ product.name }} <span class="pull-right">{{ product.cost }}</span></li>
			{% endif %}
		{% endfor %}
					</ul>
				</div>
			</div>
	{% endfor %}	
		</div>
	</div>
</div>
</div>

## Individual agency fare products

<div class="row">
	<div class="col-sm-6">
		<p>
			In addition to the Breeze Card, GRTA Xpress, CCT, and GCT each have their own fare products to use on their services. 
		</p>
		<p>
			Riders may choose to purchase passes from each transit service directly. Passes can be purchased from each individual agency at the links below.
		</p>
	</div>
	<div class="col-sm-6">
		<div class="row">
			{% for agency in site.data.fares %}
			{% if agency.info_url %}
			<div class="col-xs-6">
				<div class="thumbnail">
					<div class="caption">
						<h3>{{ agency.name }}</h3>
						<a class="btn btn-primary top-buffer" target="_blank" href="{{ agency.info_url }}" alt="Fare information" title="Fare information"><i class="fa fa-info-circle"></i></a>
						<a class="btn btn-success top-buffer" target="_blank" href="{{ agency.purchase_url }}" alt="Purchase fare" title="Purchase fare"><i class="fa fa-shopping-cart"></i></a>
					</div>
				</div>
			</div>
			{% endif %}
			{% endfor %}
		</div>
	</div>
</div>


