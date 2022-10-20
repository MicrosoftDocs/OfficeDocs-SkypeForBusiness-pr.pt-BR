---
title: O que são planos de discagem?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Saiba que tipo de planos de chamada discada (planos de discagem de Chamada PSTN) estão disponíveis com o Teams e como escolher um para sua organização.  '
ms.openlocfilehash: 77ee7801d43bd6a7cf9ae9a9e3fc74c302f8caa0
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614244"
---
# <a name="what-are-dial-plans"></a>O que são planos de discagem?

Um plano de discagem é um conjunto nomeado de regras de normalização que convertem números de telefone discados por um usuário individual em um formato alternativo (normalmente E.164) para fins de autorização de chamada e roteamento de voz.

Um plano de discagem consiste em uma ou mais regras de normalização que definem como os números de telefone expressos em vários formatos são convertidos em um formato alternativo. A mesma cadeia de caracteres de discagem pode ser interpretada e traduzida de forma diferente em planos de discagem diferentes, portanto, dependendo de qual plano de discagem é atribuído a um determinado usuário, o mesmo número discado pode ser traduzido e roteado de forma diferente. Pode haver um máximo de 1.000 planos de discagem de locatário.

Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar planos de discagem de locatário.

## <a name="tenant-dial-plan-scope"></a>Escopo do plano de discagem do locatário

O escopo de um plano de discagem determina o nível hierárquico em que o plano de discagem pode ser aplicado. Os clientes obtêm o plano de discagem apropriado por meio de configurações de provisionamento que são fornecidas automaticamente quando os usuários fazem logon no Teams. Como administrador, você pode gerenciar e atribuir níveis de escopo do plano de discagem usando o Centro de administração do Microsoft Teams ou o PowerShell Remoto.

No Teams, há dois tipos de planos de discagem: no escopo do serviço e no escopo do locatário (que é para sua organização). Um plano de discagem no escopo do serviço é definido para cada país ou região em que o Sistema de Telefonia está disponível. Cada usuário recebe automaticamente o plano de discagem do país de serviço que corresponde ao local de uso atribuído ao usuário. Você não pode alterar o plano de discagem do país de serviço, mas pode criar planos de discagem com escopo de locatário, o que aumenta o plano de discagem do país de serviço. À medida que os clientes são provisionados, eles obtêm um "plano de discagem efetivo", que é uma combinação do plano de discagem do país de serviço e do plano de discagem de locatário com escopo apropriado. Portanto, não é necessário definir todas as regras de normalização nos planos de discagem do locatário, visto que eles já podem existir no plano de discagem do país de serviço.

Os planos de discagem de locatário podem ser divididos em dois escopos: escopo do locatário ou escopo do usuário. Se um locatário definir e atribuir um plano de discagem com escopo de usuário, esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem do usuário atribuído. Se um locatário definir um plano de discagem com escopo de locatário, mas não atribuir um plano de discagem com escopo de usuário, esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem do locatário.

A seguir está o modelo de herança de planos de discagem no Teams.

![Como os planos de discagem são herdados no Teams.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

A seguir são apresentados planos de discagem efetivos possíveis:

 **País do Serviço** Se nenhum plano de discagem com escopo de locatário for definido e nenhum plano de discagem com escopo de usuário do locatário for atribuído ao usuário provisionado, o usuário receberá um plano de discagem efetivo mapeado para o país de serviço associado ao local de uso.

 **Locatário Global – País de Serviço** Se um plano de discagem de usuário de locatário for definido, mas não atribuído a um usuário, o usuário provisionado receberá um plano de discagem efetivo que consiste em um plano de discagem de locatário mesclado e o plano de discagem do país de serviço associado ao local de uso.

 **Usuário do Locatário – País de Serviço** Se um plano de discagem de usuário de locatário for definido e atribuído a um usuário, o usuário provisionado receberá um plano de discagem efetivo que consiste no plano de discagem de usuário do locatário mesclado e no plano de discagem do país de serviço associado ao local de uso.

Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar seus planos de discagem de locatário.

> [!NOTE]
> No cenário em que nenhuma regra de normalização de plano de discagem se aplica a um número discado, a cadeia de caracteres discada ainda é normalizada para acrescentar "+CC", em que CC é o código do país do local de uso do usuário de discagem. Isso se aplica a planos de chamada, roteamento direto e cenários de discagem de conferência PSTN. Além disso, se uma regra de normalização do plano de discagem de locatário resultar em um número que não começa com "+", o serviço de chamada tentará normalizar o número recebido do cliente teams com base no plano de discagem do locatário e, se não for correspondido, no plano de discagem de região. Para evitar a normalização dupla, é recomendável que os clientes de Roteamento Direto normalizem números para incluir um + e, em seguida, removam o + usando regras de Tradução de Tronco. 

## <a name="planning-for-tenant-dial-plans"></a>Planejamento de planos de discagem de locatário

Para planejar os planos de discagem personalizado, siga estas etapas:

- **Etapa 1** Decida se um plano de discagem personalizado é necessário para aprimorar a experiência de discagem do usuário. Normalmente, a necessidade de um seria dar suporte à discagem não E.164, como extensões ou discagem nacional abreviada.

- **Etapa 2** Determine se os planos de discagem com escopo de usuário global ou de locatário são necessários ou ambos. Os planos de discagem de usuário com escopo serão necessários se os usuários tiverem exigências de discagem local diferentes.

- **Step 3** Identify valid number patterns for each required dial plan. Only the number patterns that are not defined in the service level country dial plans are required.

- **Step 4** Develop an organization-wide scheme for naming dial plans. Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.


## <a name="creating-your-new-dial-plan"></a>Criando seu novo plano de discagem

Quando você criar um novo plano de discagem, insira as informações necessárias.

### <a name="name-and-simple-name"></a>Nome e nome simples

Para planos de discagem do usuário, você deve especificar um nome descritivo que identifique os usuários aos quais o plano de discagem será atribuído. O Nome Simples do plano de discagem é preenchido previamente com uma cadeia de caracteres derivada do nome do plano de discagem. O campo Nome Simples é editável, o que permite a criação de uma convenção de nomenclatura mais descritiva para os planos de discagem. O valor Nome Simples não pode ficar em branco e deve ser exclusivo. Uma prática recomendada é desenvolver uma convenção de nomenclatura para a organização inteira e, em seguida, usar essa convenção de forma consistente em todos os sites e usuários.

### <a name="description"></a>Descrição

Recomendamos que você digite o nome comum e reconhecível da localização geográfica ou grupo de usuários para os quais o plano de discagem correspondente se aplica.

### <a name="external-access-prefix"></a>Prefixo de acesso externo
<a name="bkexternalprefix"> </a>

É possível especificar um prefixo de acesso externo de até quatro caracteres (#, * e 0-9) se os usuários precisam discar um ou mais dígitos adicionais (por exemplo, 9) para obter uma linha externa.

> [!NOTE]
> [!OBSERVAçãO] Se você especificar um prefixo de acesso externo, não será necessário criar uma regra de normalização adicional para acomodar o prefixo.

Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar seus planos de discagem de locatário.

## <a name="normalization-rules"></a>Regras de normalização
<a name="bknormalizationrule"> </a>

Normalization rules define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.

Uma ou mais regras de normalização devem ser atribuídas ao plano de discagem. As regras de normalização são correspondidas de cima para baixo, portanto, a ordem na qual elas aparecem em um plano de discagem de locatário é importante. Por exemplo, se um plano de discagem de locatário tiver 10 regras de normalização, será feita a lógica de correspondência de um número discado iniciando com a primeira regra de normalização, se não houver correspondência, então a segunda e assim por diante. Se for feita uma correspondência, essa regra será usada e não haverá esforço para corresponder as demais regras que estiverem definidas. Pode haver no máximo 50 regras de normalização em um determinado plano de discagem de locatário.

### <a name="determining-the-required-normalization-rules"></a>Determinação de regras de normalização necessárias

Como qualquer plano de discagem de locatário é efetivamente mesclado com o plano de discagem do país de serviço de um determinado usuário, é provável que as regras de normalização do plano de discagem do país de serviço precisem ser avaliadas para determinar quais regras de normalização do plano de discagem de locatário são necessárias. O cmdlet **Get-CsEffectiveTenantDialPlan** pode ser usado para essa finalidade. O cmdlet usa a identidade de um usuário como parâmetro de entrada e retorna todas as regras de normalização aplicáveis ao usuário.

### <a name="creating-normalization-rules"></a>Criação de regras de normalização
<a name="createrule"> </a>

As regras de normalização .NET Framework expressões regulares para especificar padrões de correspondência numérica que o servidor usa para traduzir cadeias de caracteres de discagem para o formato E.164. As regras de normalização podem ser criadas especificando a expressão regular para a correspondência e a conversão a ser feita quando uma correspondência é encontrada. Ao concluir, você pode digitar um número de teste para verificar se a regra de normalização funciona como o esperado.

Para obter detalhes sobre como .NET Framework expressões regulares, [consulte .NET Framework Expressões Regulares](/dotnet/standard/base-types/regular-expressions).

Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar regras de normalização para seus planos de discagem de locatário.

> [!NOTE]
> Atualmente, não há suporte para regras de normalização com o primeiro token como opcional em dispositivos 3pip (por exemplo, modelo Polycom VVX 601). Se você quiser aplicar regras de normalização com opcionalidade em dispositivos 3pip, deverá criar duas regras de normalização em vez de uma. Por exemplo, a regra ^0? (999)$ deve ser substituído pelas duas regras a seguir: (999)$ (Tradução:$1) e ^0(999)$ (Tradução:$1).


### <a name="sample-normalization-rules"></a>Regras de normalização de exemplo

The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.

<a name="regularexpression"> </a>
**Regras de normalização usando .NET Framework regulares**

| Nome da regra<br/> | Descrição<br/> | Padrão do número<br/> | Conversão<br/> | Exemplo<br/> |
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Converte extensões de 4 dígitos.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 é convertido em +14255550100  <br/> |
|5digitExtension  <br/> |Converte extensões de 5 dígitos.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 é convertido em +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte números de 7 dígitos para números locais Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 é convertido em +14255550100  <br/>|
|RedmondOperator  <br/> |Converte 0 para o Operador Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 é convertido em +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte números com o prefixo (6) na rede e o código de local do Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 é convertido em +14255550100  <br/> |
|5digitRange  <br/> |Converte extensões de 5 dígitos iniciando com o intervalo de dígitos de 3 a 7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+142555$1 <br/> |54567 é convertido em +14255554567  <br/> |
|PrefixAdded  <br/> |Adiciona um prefixo de país na frente de um número de 9 dígitos com restrições no primeiro e terceiro dígitos.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 é convertido em 14255554567  <br/> |
|NoTranslation  <br/> |Corresponde 5 dígitos, mas não faz a conversão.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 é convertido em 34567  <br/> |

 **Plano de discagem de Redmond com base nas regras de normalização mostradas acima.**

 A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, com base nas regras de normalização mostradas na tabela anterior.

| Plano de discagem de Redmond<br/> |
|:-----------------------|                                                                                                                      
| 5digitExtension <br/> |                                                                                                                                    
| 7digitcallingRedmond <br/> |
| RedmondSitePrefix <br/> |
| RedmondOperator <br/> |

> [!NOTE]
> Os nomes das regras de normalização mostrados na tabela anterior não incluem espaços, mas isso é uma questão de escolha. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "Extensão de 5-dígitos" e ainda assim ser válido.

## <a name="related-topics"></a>Tópicos relacionados

[Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)

[Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
