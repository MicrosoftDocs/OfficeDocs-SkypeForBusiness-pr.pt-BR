---
title: Planejar o serviço de correio de voz de nuvem | Skype PBX para Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Este artigo descreve os benefícios, considerações sobre planejamento e requisitos necessários para implementar o serviço de correio de voz de nuvem da Microsoft. Para obter informações sobre como configurar a caixa postal de nuvem, consulte Configurando o correio de voz de nuvem.
ms.openlocfilehash: e16ad9fb123342f7ac7e780f43bffd9b54b82ce6
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "29770912"
---
# <a name="plan-cloud-voicemail-service"></a>Planejar o serviço de correio de voz de nuvem

## <a name="overview"></a>Visão geral

Este artigo descreve os benefícios, considerações sobre planejamento e requisitos necessários para implementar o serviço de correio de voz do Microsoft Cloud. Para obter informações sobre como configurar a caixa postal de nuvem, consulte [serviço de configurar caixa postal de nuvem](configure-cloud-voicemail.md).

Caixa postal de nuvem assume o lugar do Exchange Unified Messaging (UM) no fornecimento de voz a funcionalidade de mensagens do Skype para usuários de voz de 2019 de negócios com caixas de correio no Exchange Server 2019 ou Exchange Online. Caixa postal de nuvem fornece os seguintes benefícios para seu local e a usuários online:

- Funcionalidade de atendimento e depositar de caixa postal com as transcrições de fala avançada

- Acesso à caixa postal na caixa de correio do Exchange do usuário usando o Skype para clientes corporativos Online ou no Outlook

- A capacidade de usar o portal do Office 365 baseado na web para gerenciar opções de caixa postal

- Suporte para caixas de correio do Exchange no local ou na nuvem

- Aproveitamento do saudações de usuário existente do Exchange Online Unified Messaging

Para obter mais informações sobre a comparação de recursos, consulte [Planejar Skype para Business Server e migração do Exchange Server](plan-um-migration.md).

Skype para Business Server 2019 continua a usar UM do Exchange para usuários cujas caixas postais estão em versões anteriores do Exchange Server (2013, 2016).  Noções básicas sobre qual solução de caixa postal será usada com base no Exchange Server e Skype para Business Server versão é uma parte importante do planejamento para a migração para um dos Skype para Business Server 2019 ou 2019 do Exchange Server. Para obter mais informações sobre migração e interoperabilidade, consulte [Planejar Skype para Business Server e migração do Exchange Server](plan-um-migration.md).

Com a caixa postal de nuvem, a suas tarefas de administração são bastante simplificadas porque:

- Não há nenhuma necessidade de configurar a função UM do Exchange.
- As tarefas de configuração para a caixa postal de nuvem são mais simples.
- Atualizações para a funcionalidade de caixa postal são entregues diretamente na nuvem, para que os usuários sempre tenham acesso aos recursos mais recentes e atualizações com menor dependência em atualizações cumulativas (CUs).
- Você tem o mesmo conjunto de controles para os locais e caixas de correio do Exchange online. Para obter mais informações sobre esses controles, consulte [Configure a caixa postal do sistema telefônico](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).

O diagrama a seguir mostra a caixa postal de nuvem em uma implantação híbrida:

![Caixa postal de nuvem SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

Chamadas não atendidas são manipuladas da seguinte maneira:  

1. Para usuários hospedados no Skype para negócios 2019 no local, as chamadas não atendidas são enviadas pelo Skype local para o Business Server para o serviço de nuvem de caixa postal online.
2. O serviço processa a caixa postal, incluindo a transcrição.
3. O serviço deposita, em seguida, a caixa postal na caixa de correio Exchange do usuário, se a caixa de correio é local ou online.  
4. Os usuários podem acessar suas mensagens de voz de qualquer um seu Skype para clientes corporativos ou do Outlook.

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressupõem que você já tem Skype para Business Server implantado em uma topologia com suporte.  Seus requisitos dependem de seu cenário:

- Se você já estiver usando UM do Exchange online e atualizar para o Skype para 2019 corporativos, você precisará modificar a política de caixa postal hospedada e verificar se os seus provedores de hospedagem estão definidas corretamente. Para obter mais informações, consulte [Configurar caixa postal de nuvem de serviço](configure-cloud-voicemail.md).

- Se você estiver usando UM do Exchange no local, ou se você tiver uma mistura de usuários usando UM do Exchange online e no local, você precisa modificará sua política de caixa postal hospedada e o provedor de hospedagem.  Para obter mais informações, consulte [Configurar caixa postal de nuvem de serviço](configure-cloud-voicemail.md).

- Para uma nova configuração da caixa postal de nuvem, siga as etapas descritas no [serviço de configurar caixa postal de nuvem](configure-cloud-voicemail.md).

Além dos requisitos acima, o abaixo requisitos devem ser configurados para se conectar ao serviço Voicemail de nuvem da Microsoft:

- Conectividade híbrida. Se você já tiver Skype para Business Server implantado e você deseja habilitar a caixa postal de nuvem para seus usuários no local, certifique-se de que você tem conectividade híbrida configurada entre seu local e ambientes on-line. Às vezes, isso é chamado uma configuração de domínio dividido.

   Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e Office 365](plan-hybrid-connectivity.md) e a [Configurar a conectividade de híbrido entre Skype para Business Server e Office 365](configure-hybrid-connectivity.md).

- No local os usuários devem ser habilitados para o Enterprise Voice e mensagens de voz hospedada no Skype para Business Server.

- Um Exchange Web Services (EWS) externo URL e descoberta automática devem ser configurada ou alguns recursos de caixa postal de nuvem serão limitados.

- Se você tiver um deployment& de local único #x 2014; ou seja, somente do Exchange e Skype para negócios servers& #x 2014; local, mas quiser tirar vantagem da caixa postal de nuvem, não será necessário licenças adicionais.

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se você estiver planejando implantar Skype para Business Server 2019 e/ou 2019 do Exchange Server, você deve planejar sua migração cuidadosamente para garantir a continuidade do serviço de mensagens de voz. Considere o seguinte:

- Exchange Server 2019 não fornece mais funcionalidade de UM do Exchange
- Skype para Business Server 2019 não são mais integra-se ao Exchange Online UM

Interoperabilidade da versão e topologias suportadas para caixa postal de nuvem estão listadas na tabela a seguir, que compara o Skype para versões Business Server o usuário pode ser hospedado em com a versão possível fornecendo suas caixas de correio do Exchange. Caixa postal de nuvem só funciona com o Skype para Business Server e Exchange Server 2019 ou Exchange Online.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype para Business Server 2019 | Unificação de mensagens do Exchange Server | Unificação de mensagens do Exchange Server | Caixa postal de nuvem | Caixa postal de nuvem
Skype for Business Server 2015 | Unificação de mensagens do Exchange Server | Unificação de mensagens do Exchange Server |  | Caixa postal de nuvem <br> Exchange Online UM * |
Lync Server 2013 <br>  | Unificação de mensagens do Exchange Server | Unificação de mensagens do Exchange Server | | Caixa postal de nuvem <br> Exchange Online UM * |

\*Até preterida. Consulte [suporte de migração Exchange Unified Messaging Online](../plan/exchange-unified-messaging-online-migration-support.md) para obter mais informações. 

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype para Business Server 2019, você pode usar UM do Exchange no Exchange Server 2013 ou 2016, mas você deve atualizar para a caixa postal de nuvem, se você estiver usando o Exchange Server 2019.
- Se você estiver atualizando para o Exchange Server 2019 e você estiver usando versões anteriores de UM do Exchange Server para Skype para mensagens de voz Business Server, a Microsoft recomenda que você atualize para Skype para Business Server 2019 antes da atualização da caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdido.

Para obter mais informações sobre como planejar sua migração, consulte [Planejar Skype para Business Server e migração do Exchange Server](plan-um-migration.md).
