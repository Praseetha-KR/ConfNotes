###Neuroimaging
- [Nipype](http://nipy.org/nipype/)
- [Nibabel](http://nipy.org/nibabel/)
- fMRI

###Simple hacks to make your Django website faster
*Premature optimization is the root of all evil* - Knuth
######SQL Optimizations:
- Double evaluation of big query
- `@cached_property` - caching for the lifetime of that query/page
- Reduce num of queries
- select_related 
- prefetch_related- does the join

	```python
	Pizza.objects.all().select_related('toppings')
	Pizza.objects.all().prefetch_related('toppings')
	```

#####Cache inside Django: 
Site, views, template fragment, session, objs, memcache, redis, db, filesystem, local mem, dummy

- `CACHE` in settings.py
- perview cache, url based cache - sets HHTP headers (Expires, Last Modified, cache control, max_age)

######Template fragments:
```
{% load cache %}
{% cache 600 homepage_footer request.user.username %}
<a href=""></a>
{% endcache %}
```

- lazy objects
- multiple cache blocks within single block

######Session cache:
`SESSION_ENGINE`

######Object cache:

```
from django.core.cache import cache
cache.set(), .get(), .delete(), .set_many()
```

- Invalidating cache: post save signal to handle cache

#####Cache outside Django: 
server, reverse proxy (Varnish), CDN(CloudFlare, Akamai), Browser

- Edge side includes: `<esi:include src="" onerror="continue" />`
- Fetch by AJAX
- Can it be done later? retry, ElasticSearch/Solr, async, large report creation
- Celery/gevent
- Micro optimizations, premature optimizations


