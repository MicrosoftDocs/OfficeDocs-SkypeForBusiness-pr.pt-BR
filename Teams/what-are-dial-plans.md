---
title: O que são planos de discagem?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Saiba como escolher uma para sua organização e que tipo de discagem chamando planos (planos de discagem PSTN chamar) estão disponíveis com o Office 365.  '
ms.openlocfilehash: d0a803316326ca4bc4909ad0e15fa4bfc75a3d00
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23889468"
---
# <a name="what-are-dial-plans"></a>O que são planos de discagem?

Um plano de discagem é um conjunto nomeado de regras de normalização que converte os números de telefone discados por um usuário em um formato alternativo (normalmente E.164) para fins de autorização e roteamento de chamadas.
  
Um plano de discagem consiste em uma ou mais regras de normalização que definem como os números de telefone expressados em vários formatos são convertidos em um formato alternativo. A mesma cadeia de caracteres de discagem pode ser interpretada e convertida de maneira diferente nos planos de discagem diferentes, portanto, dependendo de qual plano de discagem for atribuído a um usuário específico, o mesmo discado número pode ser traduzido e roteado de forma diferente.
  
Consulte [criar e gerenciar planos de discagem](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) para criar e gerenciar planos de discagem de locatário.
  
## <a name="tenant-dial-plan-scope"></a>Escopo do plano de discagem do locatário

O escopo de um plano de discagem determina o nível hierárquico em que o plano de discagem pode ser aplicado. Os escopos são diferentes vez em um Skype para Business Server 2015 implantação no local. Os clientes obtêm o plano de discagem adequado por meio de configurações de provisionamento que são fornecidas automaticamente quando os usuários se conectam ao Skype for Business Online. Como um administrador, você pode gerenciar e atribuir níveis de escopo de plano de discagem usando o PowerShell Remoto.
  
No Skype para Business Online, há dois tipos de planos de discagem - com escopo de serviço e inquilino (que é para sua organização) com escopo. Um plano de discagem no escopo do serviço é definido para cada país/região em que o sistema de telefone do Office 365 está disponível. Cada usuário é automaticamente atribuído o plano de discagem do país de serviço que coincida com o local de uso do Office 365 atribuída ao usuário. Não é possível alterar o plano de discagem do país de serviço, mas você pode criar planos de discagem no escopo de locatário, qual incrementar o plano de discagem do país de serviço. Como os clientes são provisionados, eles obtenham um "plano de discagem eficaz", que é uma combinação do plano de discagem do país de serviço e o plano de discagem de locatário apropriadamente com escopo. Portanto, não é necessário definir todas as regras de normalização nos planos de discagem do locatário, visto que eles já podem existir no plano de discagem do país de serviço.
  
Os planos de discagem do locatário podem ser divididos em dois escopos: escopo do locatário ou do usuário. Se um locatário definir e atribuir um plano de discagem de usuário com escopo, então esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem de usuário atribuído. Se um locatário definir um plano de discagem de locatário com escopo, mas não atribuir um plano de discagem de usuário com escopo, então esse usuário será provisionado com um plano de discagem efetivo do plano de discagem do país de serviço do usuário e o plano de discagem do locatário.
  
A seguir é apresentado o modelo de herança de planos de discagem no Skype for Business Online.
  
![How dial plans are inherited in Skype for Business Online.](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)
  
A seguir são apresentados planos de discagem efetivos possíveis:
  
 **País do serviço** Se nenhum plano de discagem de locatário com escopo é definido e nenhum plano de discagem do usuário no escopo do inquilino é atribuído ao usuário provisionado, o usuário receberá um plano de discagem efetivo mapeado para o país de serviço associado ao seu local de uso do Office 365.
  
 **Locatário Global - país do serviço** Se um plano de discagem do usuário de Inquilino é definido, mas não atribuído a um usuário, o usuário provisionado receberá um plano de discagem eficaz consiste em um plano de discagem de locatário mesclado e o plano de discagem do país de serviço associado ao seu local de uso do Office 365.
  
 **Usuário de Inquilino - país do serviço** Se um plano de discagem do usuário de Inquilino é definido e atribuído a um usuário, o usuário provisionado receberá um plano de discagem efetivo consistindo o plano de discagem do usuário de Inquilino mesclado e o plano de discagem do país de serviço associado ao seu local de uso do Office 365.
  
Consulte [criar e gerenciar planos de discagem](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) para criar seu locatário planos de discagem.
  
## <a name="planning-for-tenant-dial-plans"></a>Planejamento de planos de discagem de locatário

Para planejar os planos de discagem personalizado, siga estas etapas:
  
- **Etapa 1** Decida se um sinalizador de discagem plano é necessária para aprimorar o experiência de discagem de usuário. Normalmente, a necessidade de um seria dar suporte a discagem não e. 164, como extensões ou abreviados discagem nacional.
    
- **Etapa 2** Determine se o inquilino global ou planos de discagem do usuário no escopo do locatário são necessários ou ambos. Os planos de discagem de usuário com escopo serão necessários se os usuários tiverem exigências de discagem local diferentes.
    
- **Etapa 3** Identifique padrões de número válido para cada plano de discagem necessário. Somente os padrões de número que não são definidos nos planos de discagem de país de nível de serviço são necessários.
    
- **Etapa 4** Desenvolva um esquema em toda a organização para nomear os planos de discagem. A adoção de um esquema de nomenclatura padrão assegura a consistência em toda a organização e facilita a manutenção e as atualizações.
    
O [FastTrack](https://fasttrack.microsoft.com/microsoft365/capabilities?view=voice) tem recursos adicionais e os parceiros que podem ajudar a implementar planos de discagem de locatário.
  
## <a name="creating-your-new-tenant-dial-plan"></a>Criação de novo plano de discagem de locatário

Quando você criar um novo plano de discagem, insira as informações necessárias.
  
### <a name="name-and-simple-name"></a>Nome e nome simples

Para planos de discagem do usuário, você deve especificar um nome descritivo que identifica aos usuários o plano de discagem será atribuído. O Nome Simples do plano de discagem é preenchido previamente com uma sequência de caracteres que é derivada do nome do plano de discagem. O campo Nome Simples é editável, o que permite a criação de uma convenção de nomenclatura mais descritiva para os planos de discagem. O valor Nome Simples não pode ficar em branco e deve ser exclusivo. Uma prática recomendada é desenvolver uma convenção de nomenclatura para a organização inteira e, em seguida, usar essa convenção de forma consistente em todos os sites e usuários.
  
### <a name="description"></a>Descrição

Recomendamos que você digite o nome comum e reconhecível da localização geográfica ou grupo de usuários para os quais o plano de discagem correspondente se aplica.
  
### <a name="external-access-prefix"></a>Prefixo de acesso externo

> [!CAUTION]
> [!CUIDADO] O prefixo de acesso externo não tem suporte atualmente 
  
É possível especificar um prefixo de acesso externo de até quatro caracteres (#, * e 0-9) se os usuários precisam discar um ou mais dígitos adicionais (por exemplo, 9) para obter uma linha externa.
  
> [!NOTE]
> [!OBSERVAçãO] Se você especificar um prefixo de acesso externo, não será necessário criar uma regra de normalização adicional para acomodar o prefixo. 
  
Consulte [criar e gerenciar planos de discagem](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) para criar seu locatário planos de discagem.
  
## <a name="normalization-rules"></a>Regras de normalização

As regras de normalização definem como os números de telefone expressos em vários formatos devem ser convertidos. A mesma sequência de números pode ser interpretada e convertida de modos diferentes dependendo do local de onde for discada. As regras de normalização podem ser necessárias, se os usuários precisarem discar números internos ou externos abreviados.
  
Uma ou mais regras de normalização devem ser atribuídas ao plano de discagem. Regras de normalização são comparadas de cima para baixo, portanto, a ordem em que aparecem em um plano de discagem de Inquilino é importante. Por exemplo, se um plano de discagem de locatário tiver 10 regras de normalização, será feita a lógica de correspondência de um número discado iniciando com a primeira regra de normalização, se não houver correspondência, então a segunda e assim por diante. Se for feita uma correspondência, essa regra será usada e não haverá esforço para corresponder as demais regras que estiverem definidas. Podem existir no máximo 25 regras de normalização em um determinado plano de discagem de locatário.
  
### <a name="determining-the-required-normalization-rules"></a>Determinação de regras de normalização necessárias

Como qualquer plano de discagem de locatário é combinado efetivamente com um plano de discagem do país de serviço de um usuário específico, é provável que as regras de normalização do plano de discagem do país do serviço sejam avaliadas para determinar quais regras de normalização do plano de discagem do locatário são necessárias. O cmdlet **Get-CsEffectiveTenantDialPlan** pode ser usado para essa finalidade. O cmdlet usa a identidade de um usuário como parâmetro de entrada e retorna todas as regras de normalização aplicáveis ao usuário.
  
### <a name="creating-normalization-rules"></a>Criação de regras de normalização

As regras de normalização usam as expressões regulares do .NET Framework para especificar os padrões de correspondência numérica que o servidor usa para converter as sequências de caracteres de discagem para o formato E.164 com a finalidade de executar uma consulta reversa de número. As regras de normalização podem ser criadas especificando a expressão regular para a correspondência e a conversão a ser feita quando uma correspondência é encontrada. Ao concluir, você pode digitar um número de teste para verificar se a regra de normalização funciona como o esperado.
  
Para obter detalhes sobre como usar expressões regulares do .NET Framework, consulte [Expressões regulares do .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
Consulte [criar e gerenciar planos de discagem](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans) para criar e gerenciar a normalização regras para seu locatário planos de discagem.
  
### <a name="sample-normalization-rules"></a>Regras de normalização de exemplo

A tabela a seguir mostra exemplos de regras de normalização que são gravadas como expressões reguladores do .NET Framework. São apenas exemplos e não deve ser uma referência prescritiva para a criação de regras de normalização.
  
 **Regras de normalização usando expressões regulares do .NET Framework**
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Nome da regra** <br/> |**Descrição** <br/> |**Padrão de número** <br/> |**Conversão** <br/> |**Exemplo** <br/> |
|4digitExtension  <br/> |Converte extensões de 4 dígitos.  <br/> |^ (\\d{4}) $  <br/> |+1425555$1  <br/> |0100 é convertido em +14255550100  <br/> |
|5digitExtension  <br/> |Converte extensões de 5 dígitos.  <br/> |^ 5 (\\d{4}) $  <br/> |+1425555$1  <br/> |50100 é convertido em +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Converte números de 7 dígitos para números locais Redmond.  <br/> |^ (\\d{7}) $  <br/> |+1425$1  <br/> |5550100 é convertido em +14255550100  <br/>|
|RedmondOperator  <br/> |Converte 0 para o Operador Redmond.  <br/> |^0$  <br/> |+14255550100  <br/> |0 é convertido em +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Converte números com o prefixo (6) na rede e o código de local do Redmond (222).  <br/> |^ 6222 (\\d{4}) $  <br/> |+1425555$1  <br/> |62220100 é convertido em +14255550100  <br/> |
|5digitRange  <br/> |Converte extensões de 5 dígitos iniciando com o intervalo de dígitos de 3 a 7 inclusive.  <br/> |^ ([3-7]\\d{4}) $  <br/> |+ 142555$ 1 <br/> |54567 é convertido em +14255554567  <br/> |
|PrefixAdded  <br/> |Adiciona um prefixo de país na frente de um número de 9 dígitos com restrições no primeiro e terceiro dígitos.  <br/> |^ ([2-9]\\d\\d [2-9]\\d{6}) $  <br/> |1$1  <br/> |4255554567 é convertido em 14255554567  <br/> |
|NoTranslation  <br/> |Corresponde 5 dígitos, mas não faz a conversão.  <br/> |^ (\\d{5}) $  <br/> |$1  <br/> |34567 é convertido em 34567  <br/> |
   
 **Plano de discagem de Redmond com base nas regras de normalização mostradas acima.**
  
A tabela a seguir ilustra um exemplo de plano de discagem para Redmond, Washington, Estados Unidos, com base nas regras de normalização mostradas na tabela anterior.
|:-----| | **Plano de discagem de Redmond** <br/> | | 5digitExtension <br/> | | 7digitcallingRedmond <br/> | | RedmondSitePrefix <br/> | | RedmondOperator <br/> |
   
> [!NOTE]
> [!OBSERVAçãO] Os nomes das regras de normalização mostrados na tabela anterior não incluem espaços, mas é uma opção. O primeiro nome da tabela, por exemplo, poderia ter sido escrito "extensão de 5 dígitos" ou "Extensão de 5-dígitos" e ainda assim ser válido. 
  

## <a name="related-topics"></a>Tópicos relacionados

[Criar e gerenciar planos de discagem](/SkypeForBusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)

[Perguntas comuns sobre a transferência de números de telefone](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[Termos e condições das chamadas de emergência](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)