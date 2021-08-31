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
description: 'Saiba que tipo de planos de chamada de discagem (planos de discagem de chamada PSTN) estão disponíveis com Teams e como escolher um para sua organização.  '
ms.openlocfilehash: 405a8902c9c367c09f7f467cb00358d75112de1f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727370"
---
# <a name="what-are-dial-plans"></a>O que são planos de discagem?

Um plano de discagem é um conjunto nomeado de regras de normalização que convertem números de telefone discados por um usuário individual em um formato alternativo (normalmente E.164) para fins de autorização de chamada e roteamento de voz.

Um plano de discagem consiste em uma ou mais regras de normalização que definem como os números de telefone expressos em vários formatos são convertidos para um formato alternativo. A mesma cadeia de caracteres de discagem pode ser interpretada e traduzida de forma diferente em planos de discagem diferentes, portanto, dependendo de qual plano de discagem é atribuído a um determinado usuário, o mesmo número discado pode ser convertido e roteado de forma diferente. Pode haver no máximo 1.000 planos de discagem de locatários.

Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar planos de discagem de locatários.

## <a name="tenant-dial-plan-scope"></a>Escopo do plano de discagem do locatário

O escopo de um plano de discagem determina o nível hierárquico em que o plano de discagem pode ser aplicado. Os clientes obterão o plano de discagem apropriado por meio das configurações de provisionamento que são fornecidas automaticamente quando os usuários fazem logo Teams. Como administrador, você pode gerenciar e atribuir níveis de escopo do plano de discagem usando o centro de administração Microsoft Teams ou o PowerShell Remoto.

Em Teams, há dois tipos de planos de discagem: escopo de serviço e escopo de locatário (que é para sua organização). Um plano de discagem com escopo de serviço é definido para cada país ou região onde Sistema de Telefonia está disponível. Cada usuário recebe automaticamente o plano de discagem do país de serviço que corresponde ao local de uso atribuído ao usuário. Você não pode alterar o plano de discagem do país de serviço, mas pode criar planos de discagem com escopo de locatário, o que aumenta o plano de discagem do país de serviço. À medida que os clientes são provisionados, eles obtém um "plano de discagem efetivo", que é uma combinação do plano de discagem do país de serviço e do plano de discagem de locatário com escopo apropriado. Portanto, não é necessário definir todas as regras de normalização nos planos de discagem do locatário, visto que eles já podem existir no plano de discagem do país de serviço.

Os planos de discagem de locatários podem ser divididos em dois escopos : escopo de locatário ou escopo do usuário. Se um locatário definir e atribuir um plano de discagem com escopo de usuário, esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem do usuário atribuído. Se um locatário definir um plano de discagem com escopo de locatário, mas não atribuir um plano de discagem com escopo de usuário, esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem de locatário.

A seguir está o modelo de herança de planos de discagem Teams.

![Como os planos de discagem são herdados Teams.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

A seguir são apresentados planos de discagem efetivos possíveis:

 **País do Serviço** Se nenhum plano de discagem com escopo de locatário for definido e nenhum plano de discagem com escopo de locatário for atribuído ao usuário provisionado, o usuário receberá um plano de discagem efetivo mapeado para o país de serviço associado ao local de uso.

 **Locatário Global - País de Serviço** Se um plano de discagem de usuário de locatário for definido, mas não atribuído a um usuário, o usuário provisionado receberá um plano de discagem efetivo que consiste em um plano de discagem de locatário mesclado e o plano de discagem do país de serviço associado ao local de uso.

 **Usuário do Locatário - País de Serviço** Se um plano de discagem de usuário de locatário for definido e atribuído a um usuário, o usuário provisionado receberá um plano de discagem efetivo que consiste no plano de discagem do usuário de locatário mesclado e no plano de discagem do país de serviço associado ao local de uso.

Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar seus planos de discagem de locatário.

> [!NOTE]
> No cenário em que nenhuma regra de normalização do plano de discagem se aplica a um número discado, a cadeia de caracteres discada ainda é normalizada para pré-anexar "+CC" onde CC é o código de país do local de uso do usuário de discagem. Isso se aplica a planos de chamadas, roteamento direto e cenários de discagem de conferência PSTN. Além disso, se uma regra de normalização do plano de discagem de locatário resulta em um número que não começa com "+", o serviço de chamada tentará normalizar o número recebido do cliente Teams com base no plano de discagem do locatário e, se não for corresponder, no plano de discagem da região. Para evitar a normalização dupla, é recomendável que os clientes de Roteamento Direto normalizem números para incluir um + e, em seguida, removam o + usando regras de Tradução de Tronco. 

## <a name="planning-for-tenant-dial-plans"></a>Planejamento de planos de discagem de locatário

Para planejar os planos de discagem personalizado, siga estas etapas:

- **Etapa 1** Decida se um plano de discagem personalizado é necessário para aprimorar a experiência de discagem do usuário. Normalmente, a necessidade de um seria dar suporte à discagem não-E.164, como extensões ou discagem nacional abreviada.

- **Etapa 2** Determine se os planos de discagem globais ou de locatários com escopo de usuário são necessários ou ambos. Os planos de discagem de usuário com escopo serão necessários se os usuários tiverem exigências de discagem local diferentes.

- **Etapa 3** Identifique padrões de número válido para cada plano de discagem necessário. Somente os padrões de número que não são definidos nos planos de discagem de país de nível de serviço são necessários.

- **Etapa 4** Desenvolva um esquema em toda a organização para nomear os planos de discagem. A adoção de um esquema de nomenclatura padrão assegura a consistência em toda a organização e facilita a manutenção e as atualizações.


## <a name="creating-your-new-dial-plan"></a>Criando seu novo plano de discagem

Quando você criar um novo plano de discagem, insira as informações necessárias.

### <a name="name-and-simple-name"></a>Nome e nome simples

Para planos de discagem de usuário, você deve especificar um nome descritivo que identifique os usuários aos quais o plano de discagem será atribuído. O plano de discagem Nome Simples é pré-preenchido com uma cadeia de caracteres derivada do nome do plano de discagem. O campo Nome Simples é editável, o que permite a criação de uma convenção de nomenclatura mais descritiva para os planos de discagem. O valor Nome Simples não pode ficar em branco e deve ser exclusivo. Uma prática recomendada é desenvolver uma convenção de nomenclatura para a organização inteira e, em seguida, usar essa convenção de forma consistente em todos os sites e usuários.

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

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser convertidos. A mesma sequência de números pode ser interpretada e convertida de modos diferentes dependendo do local de onde for discada. As regras de normalização podem ser necessárias, se os usuários precisarem discar números internos ou externos abreviados.

Uma ou mais regras de normalização devem ser atribuídas ao plano de discagem. As regras de normalização são corresponder de cima para baixo, portanto, a ordem na qual elas aparecem em um plano de discagem de locatário é importante. Por exemplo, se um plano de discagem de locatário tiver 10 regras de normalização, será feita a lógica de correspondência de um número discado iniciando com a primeira regra de normalização, se não houver correspondência, então a segunda e assim por diante. Se for feita uma correspondência, essa regra será usada e não haverá esforço para corresponder as demais regras que estiverem definidas. Pode haver no máximo 50 regras de normalização em um determinado plano de discagem de locatário.

### <a name="determining-the-required-normalization-rules"></a>Determinação de regras de normalização necessárias

Como qualquer plano de discagem de locatário é efetivamente mesclado com o plano de discagem do país de serviço de um determinado usuário, é provável que as regras de normalização do plano de discagem do país de serviço precisem ser avaliadas para determinar quais regras de normalização do plano de discagem de locatário são necessárias. O cmdlet **Get-CsEffectiveTenantDialPlan** pode ser usado para essa finalidade. O cmdlet usa a identidade de um usuário como parâmetro de entrada e retorna todas as regras de normalização aplicáveis ao usuário.

### <a name="creating-normalization-rules"></a>Criação de regras de normalização
<a name="createrule"> </a>

As regras de normalização usam .NET Framework expressões regulares para especificar padrões de combinação numérica que o servidor usa para traduzir cadeias de caracteres de discagem para o formato E.164. As regras de normalização podem ser criadas especificando a expressão regular para a correspondência e a conversão a ser feita quando uma correspondência é encontrada. Ao concluir, você pode digitar um número de teste para verificar se a regra de normalização funciona como o esperado.

Para obter detalhes sobre como usar .NET Framework expressões regulares, [consulte .NET Framework Expressões Regulares](/dotnet/standard/base-types/regular-expressions).

Consulte [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar regras de normalização para seus planos de discagem de locatários.

> [!NOTE]
> No momento, as regras de normalização com o primeiro token como opcional não são suportadas em dispositivos 3pip (por exemplo, modelo Polycom VVX 601). Se você quiser aplicar regras de normalização com opcionalidade em dispositivos 3pip, crie duas regras de normalização em vez de uma. Por exemplo, a regra ^0? (999)$ deve ser substituído pelas duas regras a seguir: (999)$ (Translation:$1) e ^0(999)$ (Translation:$1).


### <a name="sample-normalization-rules"></a>Regras de normalização de exemplo

A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.

<a name="regularexpression"> </a> 
 **Regras de normalização usando .NET Framework expressões regulares**

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
> Os nomes de regras de normalização mostrados na tabela anterior não incluem espaços, mas isso é uma questão de escolha. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "Extensão de 5-dígitos" e ainda assim ser válido.

## <a name="related-topics"></a>Tópicos relacionados

[Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)

[Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
