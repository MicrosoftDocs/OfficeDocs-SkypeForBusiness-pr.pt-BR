---
title: Planejar conferência discda em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Resumo: leia este tópico para saber mais sobre o planejamento da conferência discagem no Skype for Business Server.'
ms.openlocfilehash: 84d034ba358213a0f79548df6cc1ca027098633b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841083"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Planejar conferência discda em Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre o planejamento da conferência discagem no Skype for Business Server.
  
A conferência discada é um recurso opcional da Skype for Business Server que permite que os participantes da reunião participem da parte de áudio de uma reunião ligando para a reunião de um telefone. A conferência discada é um subconjunto da conferência de áudio e exige configuração adicional. Este tópico descreve o que você precisa pensar antes de implantar a conferência discagem para sua organização. 
  
Alguns dos componentes necessários para conferência discada são específicos para conferência discada e alguns são Enterprise Voice componentes. Embora a conferência discado use alguns dos mesmos componentes que Enterprise Voice usa, você pode implantar a conferência discagem mesmo que você não implante Enterprise Voice. Esta seção descreve os componentes necessários para conferência discagem. Para obter mais informações sobre como planejar uma solução de Enterprise Voice completa, consulte [Plan your Enterprise Voice solution in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
A conferência discada exige que você forneça conectividade à PSTN (rede telefônica pública comutado) implantando um Servidor de Mediação. Além de implantar um Servidor de Mediação, você precisa considerar o seguinte para permitir conferência discada para sua organização:
  
- Seu plano de conexão com a PSTN (rede telefônica pública comutado)
    
- Seu plano para planos de discagem, números de acesso e regiões de conferência
    
- Seu plano para criar diretórios de conferência
    
- Sua política de conferência para permitir o acesso discado
    
- Suporte para usuários corporativos e anônimos
    
> [!NOTE]
> Se você implantar a conferência discado, deverá implantá-la em todos os pools onde você Skype for Business Server conferência. Você não precisa atribuir números de acesso, os números que os participantes chamam para ingressar em uma conferência em cada pool, mas você deve implantar o recurso de discagem em cada pool. Esse requisito dá suporte ao recurso de nome gravado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência Skype for Business Server em um pool diferente. 
  
## <a name="plan-for-pstn-connectivity"></a>Planejar conectividade PSTN

A conferência discagem requer pelo menos um Servidor de Mediação e pelo menos um gateway PSTN (rede telefônica pública comutado). 
  
Você pode implantar um Servidor de Mediação em um site central ou em um site de filial. Em um site central, você pode colocar um Servidor de Mediação em um pool de Front-End ou Edição Standard servidor, ou pode implantá-lo em um servidor ou pool autônomo. Em um site de filial, você pode implantar um Servidor de Mediação em um servidor autônomo ou como um componente do Aparelho de Filial Suportável.
  
Você pode implantar um gateway PSTN em um site central ou em um site de filial. Em um site de filial, o gateway PSTN pode ser autônomo ou um componente do Aparelho de Filial Suportável.
  
Para obter detalhes sobre os requisitos de gateway PSTN e Servidor de Mediação, consulte Componente do Servidor de Mediação no [Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), Implantar um Servidor de Mediação no Construtor de [Topologias](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)no Skype for Business Server e Definir um gateway no Construtor de [Topologias em Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Planejar planos de discagem, números de acesso e regiões de conferência

Para configurar a conferência discagem, crie planos de discagem e números de acesso de conferência discado. Você também especifica as regiões discadas que associam um número de acesso de conferência discado aos seus planos de discagem. Mais especificamente:
  
- Planos de discagem são conjuntos de regras de normalização que especificam o número e o padrão de dígitos em um número de telefone e traduzem o número de telefone para o formato padrão E.164 necessário para roteamento de chamadas.
    
- Os números de acesso à conferência discagem são os números que os participantes chamam para ingressar em uma conferência.
    
- Cada número de acesso de conferência discada deve estar associado a pelo menos um plano de discagem. 
    
- Cada plano de discagem está associado a uma região de conferência.
    
Ao criar um plano de discagem, especifique a região de conferência discagem que se aplica ao plano de discagem. Ao criar o número de acesso discado, selecione as regiões que associam o número de acesso aos planos de discagem apropriados.
  
Você também especifica o escopo do plano de discagem: escopo do usuário, escopo do pool ou escopo do site. Cada usuário recebe o plano de discagem do escopo mais estreito que se aplica ao usuário. Por exemplo, um usuário recebe um plano de discagem no nível do usuário, se um se aplicar. Se um plano de discagem no nível do usuário não se aplicar, o usuário recebe um plano de discagem no nível do pool. Se um plano de discagem no nível do pool não se aplicar, o usuário recebe um plano de discagem no nível do site. Se um plano de discagem no nível do site não for aplicado, o usuário será atribuído ao plano de discagem global. 
  
Antes de configurar os planos de discagem, é importante planejar como deseja nomear e usar regiões. As seguintes considerações se aplicam a regiões de conferência discadas:
  
- Uma região geralmente é uma área geográfica associada a um escritório ou grupo de escritórios.
    
- Os idiomas são associados aos números de acesso discado. Se você suporta áreas geográficas com vários idiomas, você deve decidir como deseja definir regiões para dar suporte aos vários idiomas. Por exemplo, você pode definir várias regiões com base em uma combinação de geografia e idioma, ou pode definir uma única região com base na geografia e ter um número de acesso discado diferente para cada idioma.
    
- Quando um usuário agenda uma reunião, por padrão, a reunião usa a região especificada pelo plano de discagem desse usuário.
    
- Por padrão, todos os números de acesso discado para a região são incluídos no convite da reunião.
    
- É importante nomear regiões para que elas sejam claramente reconhecíveis. O usuário pode usar os nomes das regiões para alterar a região de uma reunião para que diferentes números de acesso sejam incluídos no convite. (Quando os usuários usam Outlook para agendar uma reunião, o usuário usa o Complemento de Reunião Online para Skype for Business alterar a região).
    
- As regiões devem ser projetadas para que qualquer convidado que queira discar para uma conferência possa ver um número de acesso local no convite de conferência.
    
- Você pode configurar a ordem na qual os números de acesso em uma região aparecem na página Configurações conferência discada (e, portanto, a ordem na qual eles aparecem no convite de conferência) usando cmdlets do Shell de Gerenciamento Skype for Business Server.
    
- Qualquer usuário de qualquer local pode chamar qualquer número de acesso discado para ingressar em uma conferência.
    
Para obter mais informações sobre como criar um plano de discagem, consulte [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and Create or modify a [normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planejar diretórios de conferência

Os diretórios de conferência mantêm um mapeamento entre a ID de reunião alfanumérico que um participante usa para ingressar em uma conferência ao usar Skype for Business e a ID de conferência somente numérica que um participante de conferência discada usa para ingressar na conferência. O formato da ID da conferência é o seguinte:
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


A criação de vários diretórios de conferência garantirá que as IDs de conferência permaneçam curtas até que uma quantidade significativa de conferências tenha sido criada. Em uma organização com um número típico de conferências por usuário, recomendamos que você crie um diretório de conferência para cada 999 usuários no pool. Usando essa diretriz, as IDs de conferência geralmente podem ser mantidas pequenas. No entanto, quando o número de diretórios de conferência (entre os pools) exceder 9, o número de ID da Conferência aumentará para dar suporte a conferências adicionais.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planejar uma política de conferência que permita o acesso de discagem

As conferências devem ser habilitadas para acesso de discagem ao configurar políticas de conferência. Por padrão, as conferências que estão ativadas para o acesso de discagem incluem as seguintes informações na solicitação de conferência:
  
- Uma ID de conferência numérica que identifica a conferência
    
- Um ou mais números de acesso PSTN
    
- Um link para uma página de conferência discada Configurações, que contém uma lista completa de números de acesso com seus idiomas associados; um local para criar, redefinir ou desbloquear números de identificação pessoal (PINs); e outras informações, como controles DTMF (multifrequência de tom duplo)
    
Para obter mais informações sobre políticas de conferência, consulte [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and Manage [conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Suporte para usuários corporativos e anônimos

A conferência de discagem suporta aos usuários corporativos e anônimos. Enterprise usuários têm credenciais de Serviços de Domínio do Active Directory e Skype for Business Server contas dentro de sua organização. Os usuários anônimos não têm credenciais da empresa dentro de sua organização. No contexto de conferência discada, um usuário na organização de um parceiro federado que usa o PSTN para se conectar a uma conferência é tratado como um usuário anônimo. Diferentemente de em outros contextos, para a conferência discagem os usuários federados não são autenticados.
  
Os usuários corporativos ou líderes de conferência que ingressam em uma conferência estão habilitados para o acesso de discagem discam um dos números de acesso de conferência e, em seguida, são solicitados a inserir o ID de conferência. Se um líder ainda não ingressou na reunião, os usuários podem digitar a sua extensão de comunicações unificadas (UC) (ou número de telefone completo) e PIN ou aguardar para ser admitidos pelo líder. Os organizadores de reuniões podem ingressar na reunião como líderes apenas digitando o seu PIN. O Servidor Front-End usa a combinação de número de telefone completo ou extensão e PIN para mapear exclusivamente os usuários corporativos para suas credenciais do Active Directory. Como resultado, os usuários corporativos são autenticados e identificados pelo nome da conferência. Os usuários corporativos também podem assumir um papel de conferência predefinido pelo organizador.
  
> [!NOTE]
> Enterprise usuários que discam de um telefone IP do office ou do Skype for Business Server Não são solicitados pelo número de telefone porque já estão autenticados. 
  
Os usuários anônimos que desejem ingressar em uma conferência de discagem discam um dos números de acesso de conferência e, em seguida, são solicitado a inserir o ID de conferência. Os usuários anônimos não autenticados também têm que registrar o seu nome. O nome gravado identifica os usuários não autenticados na conferência. Os usuários anônimos não são admitidos na conferência até que pelo menos um líder ou usuário autenticado ingresse e não é possível atribuir uma função predefinida.
  
> [!NOTE]
> Os usuários corporativos que optam por não inserir o número de telefone e o PIN não são autenticados. Eles serão solicitados a registrar seu nome e são tratados como usuários anônimos na conferência. 
  
Ao agendar uma reunião, o organizador da reunião pode optar por restringir o acesso à reunião, tornando a reunião fechada ou bloqueada. Nesse caso, os usuários discados são solicitados a autenticar. 
  
- Se os usuários de discagem falharem ou optarem por não autenticar, eles serão transferidos para o lobby onde até que um líder os aceite ou rejeite, ou eles se desconectam.
    
- Depois que eles são admitidos em uma conferência, os usuários de discagem podem participar da parte de áudio da conferência e podem exercer comandos DTMF (dual-tone multi-frequency) usando o teclado de telefone.
    
- Os líderes de discagem podem exercitar comandos DTMF para ativar ou desativar a capacidade dos participantes de desativar ou desativar, bloquear ou desbloquear a conferência, admitir pessoas do lobby e ativar ou desativar os comunicados de entrada e saída.
    
- Os líderes também podem usar um comando DTMF para admitir todos do lobby, o que altera as permissões da reunião para permitir que qualquer pessoa que se inscreva subsequentemente. 
    
- Todos os participantes de discagem podem exercitar comandos DTMF para ouvir Ajuda, ouvir a lista de conferências e silenciar a si mesmos.
    
- Os participantes discados (isto é, se eles discam ou não da PSTN) ouvem comunicados pessoais durante a conferência, como se eles foram mudos ou não, se a reunião está sendo gravada ou se alguém está aguardando no lobby.
    
    > [!NOTE]
    > Os participantes que ingressam na conferência clicando em um link, em vez de discando, não ouvem os comunicados pessoais. 
  

