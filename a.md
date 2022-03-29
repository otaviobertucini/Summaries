# Envio do tracking do CT-e

- Esse endpoint é o responsável por receber o status do tracking do CT-e "guarda-chuva".
## Parâmetros do body

| Parâmetro    | Tipo    | Obrigatoriedade | Descrição |
| ------------ | ------- | --------------- | --------- |
| cte_key  | string | *Obrigatório.* | Chave do CT-e |
| status_code    | string | *Obrigatório* | Status referente ao código da tabela [Status Object](#status-object) |


### Exemplo de body

```json
{
    "cte_key": "26200681800849006182570030000743501000743508",
    "status_code": "000"
}
```

### Retorno

- O retorno da `API` em caso de sucesso será o status 204.



## Erros
- O retorno da API em caso de erro poderá ser 400 ou 404

### Exemplo de body 404
Ou cte_key ou status_code não encontrado. 

status_code não encontrado:
```json
{
    "cte_key": "26200681800849006182570030000743501000743508",
    "status_code": "999"
}
```

### Exemplo de body 400
Ou cte_key ou status_code inválido:

```json
{
    "cte_key": null,
    "status_code": null
}
```


## Status Object
| Slug | Descrição   | Código |
| ----- | ------ | ------ | 
| DELIVERED|Entrega Realizada Normalmente|001| 
| CLARIFY_DELIVERY_FAIL|Mercadoria em Desacordo com o Pedido Compra|009| 
| CLARIFY_DELIVERY_FAIL|Falta de Espaço Físico no Depósito do Cliente Destino|005| 
| CLARIFY_DELIVERY_FAIL|Endereço do Cliente Destino não Localizado|006| 
| CLARIFY_DELIVERY_FAIL|Preço Mercadoria em Desacordo com o Pedido Compra|008| 
| CLARIFY_DELIVERY_FAIL|Recusa por Pedido de Compra Cancelado|004| 
| CLARIFY_DELIVERY_FAIL|Devolução não Autorizada pelo Cliente|007| 
| IN_TRANSIT|Processo de Transporte já Iniciado|000| 
| DELIVERED|Entrega Fora da Data Programada|002| 
| CLARIFY_DELIVERY_FAIL|Recusa por Falta de Pedido de Compra|003| 
| DELIVERY_FAILED|Recusa por Deficiência Embalagem Mercadoria|011| 
| CLARIFY_DELIVERY_FAIL|Cliente Destino somente Recebe Mercadoria com Frete Pago|01| 0
| INTERNAL_STATUS|Transportadora não Atende a Cidade do Cliente Destino|013| 
| DELIVERY_FAILED|Mercadoria fora da Embalagem de Atacadista|017| 
| INTERNAL_STATUS|Mercadorias Trocadas|018| 
| INTERNAL_STATUS|Pedido de Compras em Duplicidade|016| 
| INTERNAL_STATUS|Redespacho não Indicado|012| 
| IN_TRANSIT|Entrega Prejudicada por Horário/Falta de Tempo Hábil|020| 
| DELIVERY_FAILED|Mercadoria Sinistrada|014| 
| IN_TRANSIT|Reentrega sem Cobrança do Cliente|022| 
| DELIVERY_FAILED|Embalagem Sinistrada|015| 
| IN_TRANSIT|Reentrega Solicitada pelo Cliente|019| 
| CLARIFY_DELIVERY_FAIL|Estabelecimento Fechado|021| 
| DELIVERY_FAILED|Roubo de Carga|027| 
| INTERNAL_STATUS|Extravio de Mercadoria em Trânsito|023| 
| DELIVERED|Mercadoria Reentregue ao Cliente Destino|024| 
| DELIVERY_FAILED|Nota Fiscal Retida pela Fiscalização|026| 
| TO_BE_DELIVERED|Cliente Retira Mercadoria na Transportadora|029| 
| CLARIFY_DELIVERY_FAIL|Cliente Fechado para Balanço|034| 
| INTERNAL_STATUS|Quantidade de Produto em Desacordo (Nota Fiscal e/ou Pedido)|035| 
| INTERNAL_STATUS|Mercadoria Retida até Segunda Ordem|028| 
| DELIVERY_FAILED|Extravio de carga pela Cia. Aérea – Cód. Aéreo|037| 
| INTERNAL_STATUS|Problema com a Documentação (Nota Fiscal e/ou CTRC)|030| 
| DELIVERED|Entrega com Indenização Efetuada|031| 
| DELIVERY_FAILED|Falta com Busca/Reconferência|033| 
| DELIVERED|Mercadoria Devolvida ao Cliente de Origem|025| 
| DELIVERY_FAILED|Extravio de documentos pela Cia. Aérea - Cód. Aéreo|036| 
| DELIVERY_FAILED|Falta com Solicitação de Reposição|032| 
| DELIVERY_FAILED|Corte de carga na pista–Cód. Aéreo|039| 
| INTERNAL_STATUS|Nota Fiscal com Produtos de Setores Diferentes|042| 
| INTERNAL_STATUS|Pedido de Compra Incompleto|041| 
| DELIVERY_FAILED|Feriado Local/Nacional|043| 
| DELIVERY_FAILED|Aeroporto fechado na origem - Cód. Aéreo|040| 
| CLARIFY_DELIVERY_FAIL|Responsável de Recebimento Ausente|046| 
| INTERNAL_STATUS|Excesso de Veículos|044| 
| CLARIFY_DELIVERY_FAIL|Cliente Destino em Greve|047| 
| CLARIFY_DELIVERY_FAIL|Cliente Destino Encerrou Atividades|045| 
| DELIVERY_FAILED|Greve nacional (Greve Geral)|050| 
| DELIVERY_FAILED|Vôo cancelado - Cód. Transp. Aéreo|049| 
| DELIVERY_FAILED|Aeroporto fechado no destino - Cód. Aéreo|048| 
| IN_TRANSIT|Mercadoria Redespachada (Entregue para Redespacho)|052| 
| DELIVERY_FAILED|Mercadoria Vencida (Data de Validade Expirada)|051| 
| IN_TRANSIT|Mercadoria não foi Embarcada Permanecendo na Origem|053| 
| DELIVERY_FAILED|Cliente não Aceita Mercadoria com Pagamento de Reembolso|056| 
| IN_TRANSIT|Mercadoria Embarcada sem CTRC ou CTRC não Embarcado|054| 
| INTERNAL_STATUS|Quebra do Veiculo de Entrega|058| 
| DELIVERY_FAILED|Endereço Transp. de Redespacho não localizado/não informado|055| 
| INTERNAL_STATUS|Recusa da Carga por Valor de Frete Errado|062| 
| INTERNAL_STATUS|Transp. não atende a cidade da transportadora de redespacho|057| 
| CLARIFY_DELIVERY_FAIL|Cliente sem Verba para Pagar o Frete|059| 
| CLARIFY_DELIVERY_FAIL|Cliente sem Verba para Reembolso|061| 
| CLARIFY_DELIVERY_FAIL|Endereço de Entrega Errado|060| 
| INTERNAL_STATUS|Fins Estatísticos|067| 
| CLARIFY_DELIVERY_FAIL|Entrar em Contato com o Comprador|065| 
| CLARIFY_DELIVERY_FAIL|Cliente não Identificado/Cadastrado|064| 
| INTERNAL_STATUS|Substituição Tributária|069| 
| CLARIFY_DELIVERY_FAIL|Cliente Destino não Recebe Pedido Parcial|071| 
| CLARIFY_DELIVERY_FAIL|Redespacho somente com Frete Pago|073| 
| CLARIFY_DELIVERY_FAIL|Troca não Disponível|066| 
| INTERNAL_STATUS|Funcionário não autorizado a Receber Mercadorias|074| 
| INTERNAL_STATUS|Sistema Fora do Ar|070| 
| CLARIFY_DELIVERY_FAIL|Cliente Destino só Recebe Pedido Parcial|072| 
| INTERNAL_STATUS|Data de Entrega Diferente do Pedido|068| 
| CLARIFY_DELIVERY_FAIL|Identificação do Cliente não Informada/Enviada/Insuficiente| 063 | 
| DELIVERY_FAILED|Estrada/Entrada de Acesso Interditada|076| 
| DELIVERY_FAILED|Avaria Total|078| 
| DELIVERY_FAILED|Avaria Parcial|079| 
| DELIVERY_FAILED|Extravio Total|080| 
| DELIVERY_FAILED|Mercadoria Embarcada para Rota Indevida|075| 
| CLARIFY_DELIVERY_FAIL|Cliente Destino Mudou de Endereço|077| 
| DELIVERY_FAILED|Extravio Parcial|081| 
| INTERNAL_STATUS|Sobra de Mercadoria sem Nota Fiscal|082| 
| CLARIFY_DELIVERY_FAIL|Mercadoria Retirada para Conferência|084| 
| INTERNAL_STATUS|Excesso de Carga/Peso|086| 
| INTERNAL_STATUS|Férias Coletivas|087| 
| INTERNAL_STATUS|Recusado aguardando negociação|088| 
| DELIVERY_FAILED|Apreensão Fiscal da Mercadoria|085| 
| INTERNAL_STATUS|Aguardando refaturamento das mercadorias|089| 
| TO_BE_DELIVERED|Entrega Programada|091| 
| INTERNAL_STATUS|Aguardando carta de correção|093| 
| INTERNAL_STATUS|Recusado pelo Redespachante|090| 
| INTERNAL_STATUS|Problemas Fiscais|092| 
| DELIVERY_FAILED|Mercadoria em poder da SUFRAMA para Internação|083| 
| IN_TRANSIT|Carga aguardando vôo conexão - Cód. Transp. Aéreo|095| 
| INTERNAL_STATUS|Recusa por divergência nas condições de pagamento|094| 
| DELIVERY_FAILED|Outros tipos de ocorrências não especificados acima|099| 
| INTERNAL_STATUS|Carga com dimensão superior ao porão da aeronave - Cód. Aéreo|097| 
| DELIVERY_FAILED|Carga sem embalagem própria para transp. Aéreo - Cód. Aéreo|096| 
| IN_TRANSIT|Chegada na cidade ou filial de destino|098| 
| INTERNAL_STATUS|Devolução/não entrega a pedido transportadora de redespacho|103| 
| INTERNAL_STATUS|Devolução por não cumprimento do agendamento|100| 
| TO_BE_DELIVERED|Data da retirada em Manaus|201| 
| CLARIFY_DELIVERY_FAIL|Devolução/não entrega a pedido do embarcador|101| 
| INTERNAL_STATUS|Nome da balsa|203| 
| INTERNAL_STATUS|Placa da carreta responsável pelo transporte|202| 
| CLARIFY_DELIVERY_FAIL|Devolução/não entrega a pedido do destinatário|102| 
| INTERNAL_STATUS|Número da frota|205| 
| INTERNAL_STATUS|Data de saída de Belém|207| 
| INTERNAL_STATUS|Data de saída da Transportadora|209| 
| DELIVERED|Entrega efetuada no cliente pela Transportadora de Redespacho|105| 
| IN_TRANSIT|Entrega efetuada na Transportadora de Redespacho|104| 
| INTERNAL_STATUS|Data de chegada no Porto|210| 
| INTERNAL_STATUS|Data de saída do Porto|211| 
| INTERNAL_STATUS|Nome do empurrador|204| 
| INTERNAL_STATUS|Data de chegada em Belém|206| 
| INTERNAL_STATUS|Data de chegada na Transportadora|208| 
| INTERNAL_STATUS|Data de chegada na segunda Transportadora|212| 
| INTERNAL_STATUS|Data de chegada na segunda Transportadora|213| 
|
