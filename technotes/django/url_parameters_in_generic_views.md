Using url parameters in generic views
-------------------------------------

I'm using a Django generic DetailView to show an object. How to get it from database using any url parameter? 

E.g. 
domain.com/object/Y23ewq45
url(r'^(?P<uuid>\w{11})/', views.DetailView.as_view(), name='detail')

class DetailView(generic.DetailView): 
    ... 
    def get_object(self): 
        uuid = self.kwargs['uuid']
        return Model.objects.get(uuid=uuid)


