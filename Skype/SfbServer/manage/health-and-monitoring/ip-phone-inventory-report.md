---
title: Relatório de inventário Telefone IP no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 'Resumo: saiba mais sobre o Relatório de inventário de Telefone IP no Skype for Business Server.'
ms.openlocfilehash: be0929918909755865c524e63af47afb014de93e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410024"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>Relatório de inventário Telefone IP no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de inventário de Telefone IP no Skype for Business Server.
  
O Relatório de inventário de telefones IP relata informações sobre os telefones IP em uso no momento em sua organização. O Relatório de inventário de telefones IP fornece uma lista detalhada de telefones IP que foram usados durante o período de relatório especificado. Entre outras coisas, esse relatório permite que os administradores saibam se há algum telefone velho e desatualizado em uso que deveria ser substituído; ele também alerta os administradores para o fato de que há telefones caros na organização, que raramente são usados. Esse tipo de informação pode ser inestimável quando se trata de comprar novos telefones ou redistribuir os existentes. (Por exemplo, um usuário que raramente usa seu telefone caro pode pedir para trocar com um usuário que usa seu telefone com muito mais frequência).
  
Deve-se observar que esse relatório tem algumas limitações quando se trata de ser usado como um relatório de inventário verdadeiro. Por um lado, o Relatório de Telefone IP simplesmente lista todos os telefones conectados ao Skype for Business Server durante o período de tempo especificado, organizado pela última vez. Se um telefone não fizer logon durante o período de tempo especificado, então ele não será listado no relatório de inventário. Isso inclui telefones que fizeram logon antes do período de tempo iniciar e que ainda estavam logados durante esse intervalo especificado. Por exemplo, suponha que você quisesse ver todo o inventário de telefone de julho de 2015. Suponha, também, que vários telefones conectados Skype for Business Server em 30 de junho de 2015 e ainda estavam conectados a partir de 1º de julho. Esses telefones não serão exibidos no relatório de inventário do dia 1º de julho.
  
É também importante observar que o relatório de inventário pode incluir telefones que sua organização não usa mais. Por exemplo, suponha que vários telefones Fabrikam conectados ao sistema em 1º de julho de 2015; 5 dias depois, sua organização se livrou de todos os telefones Fabrikam e os substituiu por um modelo mais novo da Contoso. Os telefones da Fabrikam ainda aparecerão no relatório de "inventário" simplesmente porque eles estavam logados no sistema durante o mês de julho.
  
Além disso, o Relatório de inventário de telefones IP não relata totais resumidos de diferentes tipos de telefones. Por exemplo, suponha que você tenha 105 telefones Polycom CX600. O relatório não dirá que você tem 105 desses telefones; em vez disso, ele simplesmente vê 105 entidades separadas do Polycom CX600. A unica maneira de saber que há 105 entradas do Polycom Cx600 seria contar cada uma dessas entradas manualmente.
  
> [!TIP]
> Ou exportar os dados e usar o Microsoft Excel ou Windows PowerShell para fazer essa contagem. 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>Como acessar o Relatório de inventário de telefones IP

O Relatório de inventário de telefones IP é acessado a partir da página inicial dos Relatórios de Monitoramento. Se você clicar na métrica URI do Usuário, você pode acessar o Relatório de atividades do usuário desse usuário. Clicar na métrica Última atividade para uma chamada ponto a ponto levará você ao Relatório de detalhes de sessão ponto a ponto; clicar na mesma métrica de uma conferência levará ao Relatório de detalhes de conferência.
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Como usar melhor o Relatório de inventário de telefones IP

Se você estiver interessado apenas nas informações de uso de um tipo de telefone específico (por exemplo, "Qual é a frequência que os usuários usam um telefone Polycom CX600?"), você poderá obter essas informações diretamente do Relatório de inventário de telefones IP, filtrando esse tipo específico de telefone. No entanto, se desejar informações resumidas sobre todos os seus telefones (quantas pessoas estão usando o Polycom CX600, quantas usam o LG-Nortel IP8540, etc.), então será necessário exportar os dados e usar outro aplicativo (como Windows PowerShell) para fazer esse tipo de análise. Por exemplo, suponha que você exporte os dados para um arquivo com valores separados por vírgula (C:\Data\IP_Phone_Inventory_Report.csv). Neste caso, você poderá usar esses dois comandos para fornecer dados de resumo de todos seus telefones:
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

Que retornará dados similares a esses:
  
<pre>
Count    Name
-----    ----
  267    POLYCOM, CX700
  267    POLYCOM, CX600
  166    POLYCOM, C
   68    Microsoft, CPE
   64    LG-Nortel, IP8540
   59    Aastra, 6725ip
   37    LG-Nortel, IP
   22    POLYCOM, CX3000
   11    Microsoft, CPE_A
    9    POLYCOM, CX500
    7    Aastra, 6721ip
</pre>

Similarmente, esses dois comandos dizem quais telefones fizeram logon no sistema, mas nunca foram realmente usados para fazer uma chamada (o valor da métrica Última atividade está em branco, indicando que nunca houve nenhuma última atividade):
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

Isso retorna dados similares a esses para cada telefone que não foi usado:
  
<pre>
Manufacturer     : POLYCOM
Hardware version : CX600
MAC address      : 00-04-F2-00-01-76
User URI         : 422
User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
Last logon time  : 8/30/2010 4:44:48 PM
Last logoff time : 8/30/2010 5:59:07 PM
Last activity    :
</pre>

Outra maneira interessante de usar o Relatório de inventário de telefones IP é esse: se você tiver o endereço MAC de um telefone IP, você poderá descobrir o usuário que usou o telefone por último, simplesmente inserindo esse endereço na caixa de texto do endereço MAC. O Relatório de inventário de telefones IP irá então relatar de volta (entre outras coisas) o endereço SIP do usuário que fez o logon por último com esse telefone. Como alternativa, você pode inserir o endereço SIP do usuário (na caixa de prefixo do URI do usuário) para descobrir todos os telefones que foram usados por esse usuário.
  
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Inventário de Telefones IP permite exibir somente os telefones fabricados por uma empresa específica ou até mesmo uma versão específica desses telefones. Você também pode escolher como os dados serão agrupados. Neste caso, os registros são agrupados por hora, dia, semana ou mês.
  
A tabela seguir lista os filtros que podem ser usados com o Relatório de Inventário de Telefones IP.
  
**Filtros do Relatório de Inventário de Telefones IP**

|**Name**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Fabricante** <br/> |Nome da empresa que fabricou o telefone IP. Os valores para este filtro são preenchidos automaticamente, com base nos telefones IP que estão atualmente no banco de dados.  <br/> |
|**Versão do hardware** <br/> |Número da versão to telefone IP; usando os filtros Fabricante e Versão do hardware, é possível identificar de forma única um tipo em particular de telefone. Os valores para este filtro são preenchidos automaticamente com base nos telefones IP que estão atualmente no banco de dados.  <br/> |
|**Agente do usuário** <br/> |Identificador do software usado pelo telefone IP. Os valores para este filtro são preenchidos automaticamente com base nos telefones IP que estão atualmente no banco de dados.  <br/> |
|**Endereço MAC** <br/> |Identificador único da interface de rede no telefone IP. O endereço de Controle de Acesso de Mídia (MAC) normalmente é atribuído no momento em que o telefone é fabricado e está programado no hardware do dispositivo.  <br/> Para pesquisar registros pertencentes a um endereço MAC específico, simplesmente insira o endereço. Por exemplo:  <br/> 00-08-5D-16-16-48  <br/> Você deve inserir o endereço completo. Um endereço parcial (por exemplo, 00-08-5D) não retorna dados.  <br/> |
|**Dias antes da última atividade** <br/> | Selecione um dos seguintes valores: <br/>  [Todos] <br/>  10  <br/>  20 <br/>  30 <br/> |
|**Dias antes da hora do último logoff:** <br/> | Selecione um dos seguintes valores: <br/>  [Todos] <br/>  10  <br/>  20 <br/>  30 <br/> |
|**Prefixo URI do usuário** <br/> |Endereço SIP do usuário que utilizou o telefone IP.  <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Inventário de Telefones IP.
  
**Métricas do Relatório de Inventário de Telefones IP**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Fabricante** <br/> |Sim  <br/> |Nome da empresa que fabricou o telefone IP.  <br/> |
|**Versão do hardware** <br/> |Sim  <br/> |Número da versão do telefone IP.  <br/> |
|**Endereço MAC** <br/> |Sim  <br/> |Identificador único da interface de rede no telefone IP. O endereço MAC normalmente é atribuído no momento em que o telefone é fabricado e está programado no hardware do dispositivo.  <br/> |
|**URI do usuário** <br/> |Sim  <br/> |Endereço SIP do usuário que utilizou o telefone IP.  <br/> |
|**Agente do usuário** <br/> |Sim  <br/> |Identificador do software usado pelo telefone IP.  <br/> |
|**Horário do último logon** <br/> |Sim  <br/> |Data e hora em que o telefone IP foi conectado pela última vez Skype for Business Server.  <br/> |
|**Horário do último logoff** <br/> |Sim  <br/> |Data e hora em que o telefone IP foi conectado pela última vez Skype for Business Server.  <br/> |
|**Última atividade** <br/> |Sim  <br/> |Data e hora em que o telefone IP foi utilizado pela última vez.  <br/> |
   

