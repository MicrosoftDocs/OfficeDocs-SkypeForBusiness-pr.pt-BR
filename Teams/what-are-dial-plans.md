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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.dialplans.overview
ms.custom:
- Calling Plans
description: 'Saiba quais tipos de planos de chamada de discagem (planos de discagem de chamada PSTN) estão disponíveis com o Teams e como escolher um para a sua organização.  '
ms.openlocfilehash: f23dd2797f70b41a4bed8fd3ddc4bf467dd459db
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919284"
---
# <a name="what-are-dial-plans"></a>O que são planos de discagem?

Um plano de discagem é um conjunto nomeado de regras de normalização que converte os números de telefone discados por um usuário em um formato alternativo (normalmente E.164) para fins de autorização e roteamento de chamadas.

Um plano de discagem consiste em uma ou mais regras de normalização que definem como os números de telefone expressos em vários formatos são convertidos em um formato alternativo. A mesma cadeia de caracteres de discagem pode ser interpretada e traduzida de forma diferente em diferentes planos de discagem, de acordo com o plano de discagem atribuído a um determinado usuário, o mesmo número discado pode ser convertido e roteado de forma diferente.

Consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar planos de discagem de locatários.

## <a name="tenant-dial-plan-scope"></a>Escopo do plano de discagem do locatário

O escopo de um plano de discagem determina o nível hierárquico em que o plano de discagem pode ser aplicado. Os clientes obtêm o plano de discagem apropriado por meio das configurações de provisionamento que são fornecidas automaticamente quando os usuários entram no Microsoft Teams. Como administrador, você pode gerenciar e atribuir níveis de escopo do plano de discagem usando o centro de administração do Microsoft Teams ou o PowerShell remoto.

No Teams, há dois tipos de planos de discagem: escopo de serviço e escopo de locatários (que é para sua organização. Um plano de discagem de escopo de serviço é definido para cada país ou região onde o sistema telefônico está disponível. Cada usuário recebe automaticamente o plano de discagem do país do serviço que corresponde ao local de uso atribuído ao usuário. Não é possível alterar o plano de discagem do país do serviço, mas você pode criar planos de discagem de escopo do locatário, o que aumenta o plano de discagem do país do serviço. Como os clientes são provisionados, eles obtêm um "plano de discagem efetivo", que é uma combinação do plano de discagem do país de serviço e o plano de discagem de locatário apropriado. Portanto, não é necessário definir todas as regras de normalização nos planos de discagem do locatário, visto que eles já podem existir no plano de discagem do país de serviço.

Os planos de discagem de locatário podem ser divididos em dois escopos-escopo do locatário ou escopo do usuário. Se um locatário define e atribui um plano de discagem de escopo do usuário, esse usuário será provisionado com um plano de discagem efetivo do plano de discagem de país do serviço do usuário e o plano de discagem do usuário atribuído. Se um locatário define um plano de discagem de escopo de locatário, mas não atribui um plano de discagem de escopo do usuário, esse usuário será provisionado com um plano de discagem efetivo do plano de discagem de país do usuário e o plano de discagem do locatário.

Veja a seguir o modelo de herança de planos de discagem no Teams.

![Como os planos de discagem são herdados no Teams](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

A seguir são apresentados planos de discagem efetivos possíveis:

 **País do serviço** Se nenhum plano de discagem de escopo do locatário for definido e nenhum plano de discagem de escopo do usuário do locatário for atribuído ao usuário provisionado, o usuário receberá um plano de discagem efetivo mapeado para o país do serviço associado ao local de uso.

 **País do serviço global-locatário** Se um plano de discagem do usuário do locatário for definido, mas não atribuído a um usuário, o usuário provisionado receberá um plano de discagem efetivo que consiste em um plano de discagem de locatário mesclado e o plano de discagem do país do serviço associado ao local do uso.

 **Usuário do locatário-país do serviço** Se um plano de discagem do usuário do locatário for definido e atribuído a um usuário, o usuário provisionado receberá um plano de discagem efetivo que consiste no plano de discagem do usuário do locatário mesclado e o plano de discagem do país do serviço associado ao local do uso.

Consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar seus planos de discagem de locatários.

## <a name="planning-for-tenant-dial-plans"></a>Planejamento de planos de discagem de locatário

Para planejar os planos de discagem personalizado, siga estas etapas:

- **Etapa 1** Decida se um plano de discagem personalizado é necessário para melhorar a experiência de discagem do usuário. Geralmente, a necessidade de um seria compatível com a discagem non-E. 164, como extensões ou discagem nacional abreviada.

- **Etapa 2** Determine se os planos de discagem de escopo do usuário global ou locatário são necessários ou ambos. Os planos de discagem de usuário com escopo serão necessários se os usuários tiverem exigências de discagem local diferentes.

- **Etapa 3** Identifique padrões de número válido para cada plano de discagem necessário. Somente os padrões de número que não são definidos nos planos de discagem de país de nível de serviço são necessários.

- **Etapa 4** Desenvolva um esquema em toda a organização para nomear os planos de discagem. A adoção de um esquema de nomenclatura padrão assegura a consistência em toda a organização e facilita a manutenção e as atualizações.

O [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) tem recursos e parceiros adicionais que podem ajudá-lo a implementar planos de discagem de locatário.

## <a name="creating-your-new-tenant-dial-plan"></a>Criação de novo plano de discagem de locatário

Quando você criar um novo plano de discagem, insira as informações necessárias.

### <a name="name-and-simple-name"></a>Nome e nome simples

Para planos de discagem do usuário, você deve especificar um nome descritivo que identifique os usuários aos quais o plano de discagem será atribuído. O nome simples do plano de discagem é previamente preenchido com uma cadeia de caracteres derivada do nome do plano de discagem. O campo Nome Simples é editável, o que permite a criação de uma convenção de nomenclatura mais descritiva para os planos de discagem. O valor Nome Simples não pode ficar em branco e deve ser exclusivo. Uma prática recomendada é desenvolver uma convenção de nomenclatura para a organização inteira e, em seguida, usar essa convenção de forma consistente em todos os sites e usuários.

### <a name="description"></a>Descrição

Recomendamos que você digite o nome comum e reconhecível da localização geográfica ou grupo de usuários para os quais o plano de discagem correspondente se aplica.

### <a name="external-access-prefix"></a>Prefixo de acesso externo
<a name="bkexternalprefix"> </a>

É possível especificar um prefixo de acesso externo de até quatro caracteres (#, * e 0-9) se os usuários precisam discar um ou mais dígitos adicionais (por exemplo, 9) para obter uma linha externa.

> [!NOTE]
> [!OBSERVAçãO] Se você especificar um prefixo de acesso externo, não será necessário criar uma regra de normalização adicional para acomodar o prefixo.

Consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar seus planos de discagem de locatários.

## <a name="normalization-rules"></a>Regras de normalização
<a name="bknormalizationrule"> </a>

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser convertidos. A mesma sequência de números pode ser interpretada e convertida de modos diferentes dependendo do local de onde for discada. As regras de normalização podem ser necessárias, se os usuários precisarem discar números internos ou externos abreviados.

Uma ou mais regras de normalização devem ser atribuídas ao plano de discagem. As regras de normalização são combinadas de cima para baixo, portanto, a ordem em que elas aparecem em um plano de discagem de locatário é importante. Por exemplo, se um plano de discagem de locatário tiver 10 regras de normalização, será feita a lógica de correspondência de um número discado iniciando com a primeira regra de normalização, se não houver correspondência, então a segunda e assim por diante. Se for feita uma correspondência, essa regra será usada e não haverá esforço para corresponder as demais regras que estiverem definidas. Podem existir no máximo 25 regras de normalização em um determinado plano de discagem de locatário.

### <a name="determining-the-required-normalization-rules"></a>Determinação de regras de normalização necessárias

Como qualquer plano de discagem de locatário é combinado efetivamente com um plano de discagem do país de serviço de um usuário específico, é provável que as regras de normalização do plano de discagem do país do serviço sejam avaliadas para determinar quais regras de normalização do plano de discagem do locatário são necessárias. O cmdlet **Get-CsEffectiveTenantDialPlan** pode ser usado para essa finalidade. O cmdlet usa a identidade de um usuário como parâmetro de entrada e retorna todas as regras de normalização aplicáveis ao usuário.

### <a name="creating-normalization-rules"></a>Criação de regras de normalização
<a name="createrule"> </a> <a name="regularexpression"> </a>

As regras de normalização usam as expressões regulares do .NET Framework para especificar os padrões de correspondência numérica que o servidor usa para converter as sequências de caracteres de discagem para o formato E.164 com a finalidade de executar uma consulta reversa de número. As regras de normalização podem ser criadas especificando a expressão regular para a correspondência e a conversão a ser feita quando uma correspondência é encontrada. Ao concluir, você pode digitar um número de teste para verificar se a regra de normalização funciona como o esperado.

Para obter detalhes sobre como usar expressões regulares do .NET Framework, consulte [expressões regulares do .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).

Consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) para criar e gerenciar regras de normalização para seus planos de discagem de locatário.

### <a name="sample-normalization-rules"></a>Regras de normalização de exemplo

A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.

 **Regras de normalização usando expressões regulares do .NET Framework**<a name="#regularexpression"> </a>

||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nome da regra** <br/> |**Descrição** <br/> |**Padrão de número** <br/> |**Conversão** <br/> |**Exemplo** <br/> |
|4digitExtension  <br/> |Converte extensões de 4 dígitos.  <br/> |^(\\d{4})$  <br/> |+1425555$1  <br/> |0100 é convertido em +14255550100  <br/> |
|5digitExtension  <br/> |Converte extensões de 5 dígitos.  <br/> |^5(\\d{4})$  <br/> |+1425555$1  <br/> |50100 é convertido em +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte números de 7 dígitos para números locais Redmond.  <br/> |^(\\d{7})$  <br/> |+1425$1  <br/> |5550100 é convertido em +14255550100  <br/>|
|RedmondOperator  <br/> |Converte 0 para o Operador Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 é convertido em +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte números com o prefixo (6) na rede e o código de local do Redmond (222).  <br/> |^6222(\\d{4})$  <br/> |+1425555$1  <br/> |62220100 é convertido em +14255550100  <br/> |
|5digitRange  <br/> |Converte extensões de 5 dígitos iniciando com o intervalo de dígitos de 3 a 7 inclusive.  <br/> |^([3-7]\\d{4})$  <br/> |+ 142555 $1 <br/> |54567 é convertido em +14255554567  <br/> |
|PrefixAdded  <br/> |Adiciona um prefixo de país na frente de um número de 9 dígitos com restrições no primeiro e terceiro dígitos.  <br/> |^([2-9]\\d\\d[2-9]\\d{6})$  <br/> |1$1  <br/> |4255554567 é convertido em 14255554567  <br/> |
|Notranslation  <br/> |Corresponde 5 dígitos, mas não faz a conversão.  <br/> |^(\\d{5})$  <br/> |$1  <br/> |34567 é convertido em 34567  <br/> |

 **Plano de discagem de Redmond com base nas regras de normalização mostradas acima.**

 A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, com base nas regras de normalização mostradas na tabela anterior.

| |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Plano de discagem de Redmond** <br/>                                                                                                                              |
| 5digitExtension <br/>                                                                                                                                    |
| 7digitcallingRedmond <br/>                                                                                                                               |
| RedmondSitePrefix <br/>                                                                                                                                  |
| RedmondOperator <br/>                                                                                                                                    |

> [!NOTE]
> Os nomes das regras de normalização mostradas na tabela anterior não incluem espaços, mas essa é uma questão de escolha. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "Extensão de 5-dígitos" e ainda assim ser válido.

## <a name="related-topics"></a>Tópicos relacionados

[Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)

[Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)

[Rótulo de isenção de isenção de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
