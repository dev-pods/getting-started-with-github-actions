{% if passed %}
## Passo {{ step_number }} — Aprovado ✅

<img src="https://octodex.github.com/images/inflatocat.png" align="right" height="150px" alt="Inflatocat comemorando a aprovação do passo" />

Ótimo trabalho! Todas as verificações passaram. Aguarde: vou preparar o próximo passo e publicar as instruções em outro comentário.

{% else %}
## Passo {{ step_number }} — Precisa de um ajuste ❌

<img src="https://octodex.github.com/images/spidertocat.png" align="right" height="100px" alt="Spidertocat ajudando a encontrar o problema" />

Algumas verificações ainda não passaram. Isso faz parte do exercício: confira os itens marcados e as dicas abaixo, corrija o arquivo e envie a alteração. O próximo passo será liberado quando todas as verificações passarem.

{% endif %}

| Resultado | Verificação |
| --- | --- |
{% for result in results %}| {% if result.passed %}✅ Aprovado{% else %}❌ Ajustar{% endif %} | {{ result.description }} |
{% endfor %}

{% if tips.length %}
### Dicas
{% for tip in tips %}
- {{ tip }}
{% endfor %}
{% endif %}

[Abrir a execução da avaliação]({{ run_url }})
