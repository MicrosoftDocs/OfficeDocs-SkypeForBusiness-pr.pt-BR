---
title: 'Lync Server 2013: planos de discagem e regras de normalização'
description: 'Lync Server 2013: planos de discagem e regras de normalização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559737"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Planos de discagem e regras de normalização no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um formato padrão único (E.164) para fins de roteamento de chamadas e autorização.

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para cada local, usuário ou objeto de contato especificado. A mesma cadeia de caracteres de discagem pode ser interpretada e convertida de forma diferente, dependendo do local de onde é discada e do objeto de contato ou pessoa que está fazendo a chamada.

<div>

## <a name="dial-plan-scope"></a>Escopo do plano de discagem

Um *escopo * do plano de discagem determina o nível hierárquico no qual o plano de discagem pode ser aplicado. No Lync Server, um usuário pode ser atribuído a um plano de discagem específico por usuário. Se um plano de discagem do usuário não for atribuído, o plano de discagem do pool do Registrador é aplicado. Se não houver nenhum plano de discagem do pool do Registrador, o plano de discagem local é aplicado. Finalmente, se nenhum plano de discagem é aplicável para o usuário, o plano de discagem global é aplicado.

Os clientes obtêm níveis de escopo do plano de discagem por meio de configurações de provisionamento em banda fornecidas quando os usuários fazem logon no Lync Server. Como administrador, você pode gerenciar e atribuir níveis de escopo do plano de discagem usando o painel de controle do Lync Server.

<div>


> [!NOTE]  
> O plano de discagem de gateway PSTN (rede telefônica pública comutada) de nível de serviço é aplicado às chamadas de entrada de um gateway específico.



</div>

Os níveis de escopo do plano de discagem são definidos como a seguir:

  - **Plano de discagem do usuário:** Podem ser atribuídos a usuários individuais, grupos ou objetos de contato. Os aplicativos de voz podem pesquisar um plano de discagem por usuário quando uma chamada é recebida com o contexto de telefone definido como user-default. Para o propósito de atribuir um plano de discagem, um objeto de contato é tratado como um usuário individual.

  - **Plano de discagem do pool:** Pode ser criado no nível de serviço para qualquer gateway PSTN ou registrador em sua topologia. Para definir um plano de discagem do pool, você deve especificar o serviço (gateway PSTN ou pool do Registrador) ao qual o plano de discagem se aplica.

  - **Plano de discagem de site:** Pode ser criado para um site inteiro, exceto para qualquer usuário, grupo ou objeto de contato que receba um plano de discagem do pool ou um plano de discagem do usuário. Para definir um plano de discagem local, você deve especificar o local ao qual o plano de discagem é aplicado.

  - **Plano de discagem global:** O plano de discagem padrão instalado com o produto. É possível editar o plano de discagem global, mas não exclui-lo. Este plano de discagem se aplica a todos os usuários, grupos e objetos de contato do Enterprise Voice em sua implantação, a menos que você configure e atribua um plano de discagem com um escopo mais específico.

</div>

<div>

## <a name="planning-for-dial-plans"></a>Planejamento de planos de discagem

Para planejar um plano de discagem, siga estas etapas:

  - Listar todos os locais nos quais sua organização tem um escritório.
    
    A lista deve estar atualizada e concluída. Precisará ser revisada conforme a organização da empresa evolui. Em uma grande empresa multinacional com numerosas pequenas filiais, essa pode ser uma tarefa demorada.

  - Identificar padrões de números válidos para cada site.
    
    A parte mais demorada do planejamento de seus planos de discagem é identificar os padrões de números válidos para cada local. Em alguns casos, será possível copiar as regras de normalização gravadas para um plano de discagem a outros planos de discagem, especialmente se os locais correspondentes estão dentro do mesmo país/região ou continente. Em outros casos, as pequenas alterações em números em um plano de discagem podem ser suficientes para usá-los em outros planos de discagem.

  - Desenvolva um esquema em toda a organização para os planos de discagem de nomeação.
    
    Adotar um esquema de nomeação padrão garante a consistência em toda a organização e facilita a manutenção e as atualizações.

  - Decida se vários planos de discagem são necessários para um único local.
    
    Se sua organização mantém um único plano de discagem entre vários locais, talvez ainda seja necessário criar um plano de discagem separado para usuários do Enterprise Voice que estão migrando de um PBX (central privada de comutação telefônica) e que precisam ter suas extensões existentes retidas.

  - Decida se são necessários planos de discagem por usuário. Por exemplo, se você tiver usuários em um site de filial registrados com o site central ou se tiver usuários registrados em um aparelho de filial persistente, você pode considerar cenários de discagem especiais para tais usuários usando planos de discagem por usuário e regras de normalização. Para obter detalhes, consulte [Branch-site resiliência Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).

  - Determine o escopo do plano de discagem (como descrito anteriormente neste tópico).

Para criar um plano de discagem, especifique valores nos campos a seguir, conforme necessário, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.

<div>

## <a name="name-and-simple-name"></a>Nome e o nome simples

Para planos de discagem do usuário, você deve especificar um nome descritivo que identifique os usuários, grupos ou objetos de contato aos quais o plano de discagem será atribuído. Para planos de discagem local, o campo Nome é preenchido com o nome do local e não pode ser alterado. Para planos de discagem do pool, o campo nome é preenchido previamente com o gateway PSTN ou FQDN (nome de domínio totalmente qualificado) do pool de front-end e não pode ser alterado.

O *Nome simples* do plano de discagem é preenchido com uma sequência derivada do nome do plano de discagem. O campo nome simples é editável, o que permite que você crie uma Convenção de nomenclatura mais descritiva para os planos de discagem. O valor *Nome simples * não pode estar vazio e deve ser exclusivo. Uma prática recomendada é desenvolver uma Convenção de nomenclatura para toda a sua organização e, em seguida, usar essa Convenção de forma consistente em todos os sites e usuários.

</div>

<div>

## <a name="description"></a>Descrição

Recomendamos digitar o nome comum reconhecível da localização geográfica à qual se aplica o plano de discagem correspondente. Por exemplo, se o nome do plano de discagem for Londres.Contoso.com, a descrição recomendada seria Londres.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>Região da conferência discada

Se você estiver implantando a conferência discada, precisará especificar uma região de conferência de discagem para associar os números de acesso da conferência discada com um plano de discagem.

</div>

<div>

## <a name="external-access-prefix"></a>Prefixo de acesso externo

Você pode especificar um prefixo de acesso externo de até quatro caracteres ( \# , \* e 0-9) se os usuários precisarem discar um ou mais dígitos à esquerda adicionais (por exemplo, 9) para obter uma linha externa.

<div>


> [!NOTE]  
> Se você especificar um prefixo de acesso externo, não é necessário criar uma regra de normalização adicional para acomodar o prefixo.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>Regras de normalização

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para o local nomeado. A mesma cadeia de caracteres de número pode ser interpretada e convertida de forma diferente, dependendo da localidade da qual ela é discada. As regras de normalização são necessárias para o roteamento de chamada porque os usuários podem, e devem, usar vários formatos ao inserir números de telefone em suas listas de contatos.

A normalização de números de telefone fornecidos pelo usuário oferece um formato consistente que facilita as seguintes tarefas:

  - Corresponde a um número discado para o SIP-URI do destinatário pretendido.

  - Aplicar regras de autorização de discagem à parte de chamada.

Estes são alguns dos campos numéricos que as regras de normalização talvez precisem considerar:

  - Plano de discagem

  - Código do país

  - Código de área

  - Tamanho da extensão

  - Prefixo do local

<div>

## <a name="creating-normalization-rules"></a>Criando regras de normalização

As regras de normalização usam expressões regulares do .NET Framework para especificar padrões de correspondência numérica que o servidor usa para converter sequências de discagem para o formato E.164 para fins de pesquisa de número inverso. Você cria regras de normalização no painel de controle do Lync Server inserindo as expressões manualmente ou digitando os dígitos iniciais e o comprimento das cadeias de caracteres de discagem a serem atendidas e permitindo que o painel de controle do Lync Server gere a expressão regular correspondente para você. De qualquer forma, ao terminar, você pode inserir um número de teste para verificar se a regra de normalização funciona como esperado.

Para obter detalhes sobre o uso de expressões regulares do .NET Framework, consulte "expressões regulares do .NET Framework" em [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>Exemplos de regras de normalização

A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>Tabela 1. Regras de normalização usando expressões regulares do .NET Framework

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome da regra</th>
<th>Descrição</th>
<th>Padrão de número</th>
<th>Tradução</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>Converte extensões de 4 dígitos</p></td>
<td><p>^ (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>0100 é convertido em +14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>Converte extensões de 5 dígitos</p></td>
<td><p>^ 5 (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>50100 é convertido em +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>Converte números de 7 dígitos para números locais de Redmond</p></td>
<td><p>^ (\d {7} ) $</p></td>
<td><p>+ 1425 $1</p></td>
<td><p>5550100 é convertido em +14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>Converte números de 7 dígitos para números locais de Dallas</p></td>
<td><p>^ (\d {7} ) $</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100 é convertido em +19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>Converte números de 10 dígitos nos Estados Unidos</p></td>
<td><p>^ (\d {10} ) $</p></td>
<td><p>+ 1 $1</p></td>
<td><p>2065550100 é convertido em +12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>Converte números com prefixos de longa distância nos Estados Unidos</p></td>
<td><p>^ 1 (\d {10} ) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100 é convertido em +2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>Converte números com prefixos internacionais nos Estados Unidos</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100 é convertido em +91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>Converte 0 no operador de Redmond</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0 é convertido em +14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>Converte números com o prefixo dentro da rede (6) e o código de área de Redmond (222)</p></td>
<td><p>^ 6222 (\d {4} ) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>62220100 é convertido em +14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>Converte números com o prefixo dentro da rede (6) e o código de área de Nova York (333)</p></td>
<td><p>^ 6333 (\d {4} ) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100 é convertido em +12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>Converte números com o prefixo dentro da rede (6) e o código de área de Dallas (444)</p></td>
<td><p>^ 6444 (\d {4} ) $</p></td>
<td><p>+ 1972555 $1</p></td>
<td><p>64440100 é convertido em +19725550100</p></td>
</tr>
</tbody>
</table>


A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, baseado nas regras de normalização mostradas na tabela anterior.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>Tabela 2. Plano de discagem de Redmond com base em regras de normalização mostradas na Tabela 1

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond. forestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Os nomes das regras de normalização mostrados na tabela anterior não incluem espaços, mas é uma questão de escolha. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "extensão de 5-dígitos" e ainda ser válido.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

