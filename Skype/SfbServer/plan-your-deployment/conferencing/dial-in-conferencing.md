---
title: Planejar a conferência discada no Skype for Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Resumo: Leia este tópico para saber mais sobre o planejamento de conferência discada em Skype para Business Server.'
ms.openlocfilehash: 1b051cc757c0e55fb2f16b790921da962738ade3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973574"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Planejar a conferência discada no Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre o planejamento de conferência discada em Skype para Business Server.
  
Conferência discada é um recurso opcional do Skype para Business Server que permite que os participantes da reunião ingressar na parte de áudio de uma reunião chamando reunião de um telefone. A conferência discada é um subconjunto da conferência de áudio e exige configuração adicional. Este tópico descreve o que você precisa considerar antes de implantar a conferência discada em sua organização. 
  
Alguns dos componentes necessários para conferência discada são específicas para conferência discada e alguns componentes do Enterprise Voice. Embora a conferência discada use alguns dos mesmos componentes do Enterprise Voice, você pode implantar a conferência discada mesmo se não implantar o Enterprise Voice. Esta seção descreve os componentes necessários para a conferência discada. Para obter mais informações sobre como planejar uma solução completa do Enterprise Voice, consulte [planejar sua solução do Enterprise Voice no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
A conferência discada exige que você forneça conectividade à Rede Telefônica Pública Comutada (PSTN) com a implantação de um Servidor de Mediação. Além de implantar um Servidor de Mediação, será necessário considerar o seguinte para permitir a conferência discada em sua organização:
  
- Seu plano para se conectar à rede telefônica pública comutada (PSTN)
    
- Seu plano para planos de discagem, números de acesso e regiões de conferência
    
- Seu plano para criar diretórios de conferência
    
- Sua política de conferência para permitir acesso de discagem
    
- Suporte para usuários corporativos e anônimos
    
> [!NOTE]
> Se você implantar a conferência discada, você deverá implantá-lo em cada pool onde você implanta o Skype para conferências Business Server. Não é necessário atribuir números de acesso (os números para os quais os participantes ligam para participar de uma conferência) em cada pool, mas você deve implantar o recurso de discagem em cada pool. Esse requisito oferece suporte ao recurso de nome registrado quando um usuário disca um número de acesso de um pool para ingressar em uma Skype para conferência Business Server em um pool diferente. 
  
## <a name="plan-for-pstn-connectivity"></a>Planejamento de conectividade PSTN

A conferência discada exige pelo menos um Servidor de Mediação e pelo menos um gateway de Rede Telefônica Pública Comutada (PSTN). 
  
Você pode implantar um Servidor de Mediação em um site central ou em um site de filial. No site central, você pode colocar um Servidor de Mediação em um Pool de Front-Ends ou servidor Standard Edition, ou pode implantá-lo em um servidor ou pool autônomo. Em um site de filial, você pode implantar um Servidor de Mediação em um servidor autônomo ou como um componente do Aparelho de Filial Persistente.
  
Você pode implantar um gateway PSTN em um site central ou em um site de filial. Em um site de filial, o gateway PSTN pode ser autônomo ou um componente do Aparelho de Filial Persistente.
  
Para obter detalhes sobre o servidor de mediação e requisitos de gateway PSTN, consulte o [componente de servidor de mediação em Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [implantar um servidor de mediação no construtor de topologia no Skype para Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)e [definir um gateway na topologia Construtor de Skype para Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Planejamento para planos de discagem, números de acesso e regiões de conferência

Para configurar a conferência discada, você deve criar planos de discagem e números de acesso da conferência discada. Você também pode especificar quais regiões de discagem que associam um número de acesso de conferência discada a seus planos de discagem. Mais especificamente:
  
- Planos de discagem são conjuntos de regras de normalização que especificam o número e o padrão de dígitos em um número de telefone e traduzem o número de telefone para o padrão E.164 exigido para o roteamento de chamadas.
    
- Números de acesso de conferência discada são os números para os quais os participantes ligam para entrar em uma conferência.
    
- Todo número de acesso de conferência discada deve ser associado a no mínimo um plano de discagem. 
    
- Cada plano de discagem é associado a uma região de conferência.
    
Ao criar um plano de discagem, especifique a região de conferência discada que se aplica ao plano. Ao criar o número de acesso de discagem, selecione as regiões que associam o número de acesso aos planos de discagem apropriados.
  
Especifique também o escopo do plano de discagem: escopo de usuário, escopo de pool ou escopo de site. Todo usuário é atribuído ao plano de discagem do escopo mais estreito que se aplicar a ele. Por exemplo, um usuário é atribuído a um plano de discagem de nível de usuário, caso um se aplique. Se um plano de discagem de nível de usuário não se aplicar, o usuário é atribuído a um plano de discagem de nível de pool. Se um plano de discagem de nível de pool não se aplicar, o usuário é atribuído a um plano de discagem de nível de site. Se um plano de discagem de nível de site não se aplicar, o usuário é atribuído ao plano de discagem global. 
  
Antes de configurar os planos de discagem, é importante planejar como você deseja nomear e usar regiões. As considerações a seguir aplicam-se a regiões de conferência discada:
  
- Uma região normalmente é uma área geográfica associada a um escritório ou grupo de escritórios.
    
- Idiomas são associados a números de acesso de discagem. Se você oferecer suporte a áreas geográficas que possuam vários idiomas, deve decidir como deseja definir regiões para oferecer suporte a vários idiomas. Por exemplo, você pode definir várias regiões com base em uma combinação de geografia e idioma ou pode definir uma única região com base em geografia e ter diferentes números de acesso de discagem para cada idioma.
    
- Quando um usuário agenda uma reunião, por padrão a reunião usa a região especificada pelo plano de discagem do usuário.
    
- Por padrão, todos os números de acesso de discagem para a região são incluídos no convite da região.
    
- É importante nomear regiões para que sejam claramente reconhecíveis. O usuário pode usar estes nomes das regiões para alterar a região de uma reunião, para que diferentes números de acesso sejam incluídos no convite. (Quando os usuários utilizam o Outlook para agendar uma reunião, o usuário usa o suplemento de Reunião Online para Skype for Business para alterar a região).
    
- Regiões devem ser criadas para que qualquer convidado que deseje discar para uma conferência possa ver um número de acesso local no convite da conferência.
    
- Você pode configurar a ordem na qual o acesso números dentro de uma região aparecem na página Configurações de conferência discada (e, portanto, a ordem em que aparecem no convite da conferência) usando Skype para cmdlets do Shell de gerenciamento do servidor de negócios.
    
- Qualquer usuário de qualquer localização pode ligar para qualquer número de acesso de discagem para entrar em uma conferência.
    
Para obter mais informações sobre como criar um plano de discagem, consulte [criar ou modificar um plano de discagem no Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) e [criar ou modificar uma regra de normalização no Skype para negócios](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planejamento para diretórios de conferência

Diretórios de conferência mantêm um mapeamento entre o ID de reunião alfanuméricos que um participante usa para ingressar em uma conferência ao usar o Skype para negócios e a ID de conferência apenas numérica que um participante de conferência discada usa para ingressar na conferência. O formato do ID de conferência é como segue:
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>
```

Criar vários diretórios de conferência garantirá que os IDs de conferência sejam curtos até que uma quantidade significativa de conferências seja criada. Em uma organização com um número comum de conferências por usuário, é recomendável criar um diretório de conferência para cada 999 usuários no pool. Usando essa diretriz, os IDs podem ser geralmente mantidos pequenos. No entanto, assim que o número de diretórios de conferência (em todos os pools) ultrapassar 9, o número do ID de conferência aumentará para suportar conferências adicionais.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planejamento de uma política de conferência que permite acesso de discagem

Conferências devem ser habilitadas para acesso de discagem ao configurar políticas de conferência. Por padrão, as conferências que estão ativadas para o acesso de discagem incluem as seguintes informações na solicitação de conferência:
  
- Uma ID numérica de conferência que identifica a conferência
    
- Um ou mais números de acesso PSTN
    
- Um link para uma página Configurações de Conferência Discada, que contém uma lista completa dos números de acesso com os seus idiomas associados; um lugar para criar, redefinir ou desbloquear os números de identificação pessoal (PINs); e outras informações, como controles de multifrequência de tom dual (DTMF)
    
Para obter mais informações sobre diretivas de conferência, consulte [Configure a conferência discada no Skype para Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) e [Gerenciar políticas de conferência no Skype para Business Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Suporte para usuários corporativos e anônimos

A conferência de discagem suporta aos usuários corporativos e anônimos. Os usuários corporativos ter credenciais do Active Directory Domain Services e Skype para contas Business Server dentro da sua organização. Os usuários anônimos não têm credenciais da empresa dentro de sua organização. No contexto de conferência discada, um usuário na organização do parceiro federado que usa a PSTN para se conectar a uma conferência é tratado como um usuário anônimo. Diferentemente de em outros contextos, para a conferência discagem os usuários federados não são autenticados.
  
Os usuários corporativos ou líderes de conferência que ingressam em uma conferência estão habilitados para o acesso de discagem discam um dos números de acesso de conferência e, em seguida, são solicitados a inserir o ID de conferência. Se um líder ainda não ingressou na reunião, os usuários podem digitar a sua extensão de comunicações unificadas (UC) (ou número de telefone completo) e PIN ou aguardar para ser admitidos pelo líder. Os organizadores de reuniões podem ingressar na reunião como líderes apenas digitando o seu PIN. O Servidor de Front-End usa a combinação do número completo ou extensão de telefone e o PIN, para mapear exclusivamente os usuários corporativos para as credenciais do Active Directory. Como resultado, os usuários corporativos são autenticados e identificados pelo nome da conferência. Os usuários corporativos também podem assumir um papel de conferência predefinido pelo organizador.
  
> [!NOTE]
> Os usuários corporativos que discam a partir de um telefone IP do office ou Skype para Business Server Attendant não são solicitados para seu número de telefone, porque eles já estão autenticados. 
  
Os usuários anônimos que desejem ingressar em uma conferência de discagem discam um dos números de acesso de conferência e, em seguida, são solicitado a inserir o ID de conferência. Os usuários anônimos não autenticados também têm que registrar o seu nome. O nome gravado identifica os usuários não autenticados na conferência. Os usuários anônimos não são admitidos na conferência até que pelo menos um líder ou usuário autenticado ingresse e não é possível atribuir uma função predefinida.
  
> [!NOTE]
> Os usuários corporativos que optam por não inserir o número de telefone e o PIN não são autenticados. Eles serão solicitados a registrar seu nome e são tratados como usuários anônimos na conferência. 
  
Ao agendar uma reunião, o organizador da reunião pode optar por restringir o acesso à reunião tornando-a fechada ou bloqueada. Nesse caso, os usuários de discagem devem ser autenticados. 
  
- Se os usuários de discagem não puderem ou não quiserem ser autenticados, eles são transferidos para o lobby, onde ficam até que um líder os aceite ou rejeite, ou até que o tempo limite se esgote e eles sejam desconectadas.
    
- Depois de serem admitidos em uma conferência, os usuários de discagem podem participar do áudio da conferência e executar comandos de multifrequência de tom dual (DTMF) com o teclado do telefone.
    
- Líderes de discagem podem executar comandos DTMF para ativar ou desativar a capacidade dos participantes de desativar Mudo, bloquear ou desbloquear a conferência, admitir pessoas do lobby e ativar ou desativar os anúncios de entrada/saída.
    
- Os líderes também podem usar um comando DTMF para admitir todos do lobby, o que altera as permissões de reunião para permitir qualquer um que participe depois. 
    
- Todos os participantes de discagem podem executar comandos DTMF par ouvir a Ajuda, ouvir os participantes da conferência e ativar Mudo para si próprios.
    
- Os participantes de discagem (se eles discam ou não do PSTN) ouvem comunicados pessoais durante a conferência, como, por exemplo, se tiveram o mudo ativado ou desativado, se a reunião está sendo gravada ou alguém está aguardando no lobby.
    
    > [!NOTE]
    > Os participantes que ingressam na conferência clicando em um link, em vez de discando, não ouvem os comunicados pessoais. 
  

