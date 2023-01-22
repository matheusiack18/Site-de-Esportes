# site-de-esportes

Modificado 121
{% extends 'base.html' %}
{% block title%}PAGINA PRINCIPAL{% endblock %}


{% block content %}

<div class="container">
    <h1 class="text-center">SEJA BEM VINDO A PAGINA HOME</h1>
    <hr> 
    <div class="row mt-3">
        {% for p in produto_list %}
        <div class="col-md-4">
            <div class="m-4">
                <h4><a href="{% url 'lojaapp:produtodetalhe' p.slug %}"> {{p.titulo}} </a></h4>   
                <img src="{{p.image.url}}" alt="" class="img-fluid" stile="height: 150; object-fit: cover;" width="200">
                <p class="mt-3">De: <strike> R$ {{p.preco_mercado}}</strike> <br>Por: R$ {{p.venda}}</p>
                <a href="{% url 'lojaapp:addcarro' p.id %}" class="btn btn-success">Comprar</a>
            </div>
        </div>
        {% endfor %}
    </div>
</div>   
{% endblock %}
