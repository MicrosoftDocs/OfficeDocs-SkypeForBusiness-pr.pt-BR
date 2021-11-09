---
title: 'Lync Server 2013: Gerenciando a federação e o acesso externo ao Skype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você habilita e configura o acesso de usuário externo para controlar se usuários externos com suporte podem colaborar com usuários internos Skype for Business Server usuários.
ms.openlocfilehash: 42e0644cbad51681f979f83041e4c260788039d1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836363"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gerenciando o acesso de federação e externo Skype for Business Server

Implantar um Servidor de borda ou um pool de Borda é a primeira etapa para suportar usuários externos. Para obter detalhes sobre como implantar Servidores de Borda, consulte [Deploy Edge Server in Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Depois de instalar e configurar sua implantação interna do Skype for Business Server, os usuários internos em sua organização podem colaborar com outros usuários internos que tenham contas SIP em seus Serviços de Domínio do Active Directory (AD DS). A colaboração pode incluir o envio e recebimento de mensagens instantâneas e a atualização do status de presença e participação nas conferências (também conhecido como "reuniões). Você habilita e configura o acesso de usuário externo para controlar se usuários externos com suporte podem colaborar com usuários internos Skype for Business Server usuários. Os usuários externos podem incluir usuários remotos de sua implantação, usuários federados (incluindo usuários com suporte de provedores de serviços de mensagens instantâneas públicas (IM) e participantes anônimos em conferências.

Se sua implantação incluiu a instalação de um servidor de borda Skype for Business Server ou um pool de Borda, o escopo de possíveis tipos de comunicação será expandido com várias opções para acesso de usuário externo, comunicação com membros de outros domínios federados SIP e provedores federados SIP. Depois de configurar o Servidor de Borda ou pool de Borda, você habilita os tipos de acesso de usuário externo que deseja fornecer e configura as políticas para controlar o acesso externo. No Skype for Business Server, você habilita e configura políticas e acesso de usuários externos usando o Painel de Controle Skype for Business Server, o [Shell](../management-shell.md)de Gerenciamento Skype for Business Server ou ambos, com base nos requisitos da tarefa. 



> [!IMPORTANT]  
> Ao projetar sua configuração e políticas para acesso do usuário externo, você deve compreender a precedência das políticas e como as políticas são aplicadas. Skype for Business Server configurações de política aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.


Por padrão, nenhuma política está configurada para oferecer suporte ao acesso de usuários externos, incluindo acesso de usuários remotos, acesso de usuários federados, mesmo se você já tiver habilitado o suporte ao acesso de usuários externos na sua organização. Para controlar o uso do acesso de usuários externos, configure uma ou mais políticas, especificando o tipo de acesso de usuários externos com suporte para cada política. Isso inclui as seguintes políticas de acesso externo:

  - **Política global**   A política global é criada automaticamente quando você implanta os Servidores de Borda. Por padrão, nenhuma opção de acesso de usuário externo é ativada na política global. Para suportar o acesso do usuário externo no nível global, configure a política global para suportar um ou mais tipos de opções de acesso de usuário externo. A política global se aplica a todos os usuários da sua organização, mas as políticas do local e do usuário a substituem. Se você excluir a política global, não a removerá e sim a redefinirá para a configuração padrão.

  - **Política de local**   Você pode criar e configurar uma ou mais políticas de local para limitar o suporte do acesso de usuário externo a locais específicos. A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política. Por exemplo, se você ativar o acesso de usuário remoto na política global, pode especificar uma política de local que o desative para um local específico. Por padrão, a política de local é aplicada a todos os usuários do local, mas você pode atribuir uma política de usuário para substituir a configuração da política de local.

  - **Política do usuário**   É possível criar e configurar uma ou mais políticas do usuário para limitar o suporte para acesso do usuário remoto aos usuários específicos. A configuração na política de usuário substituir a política global e local, mas apenas para os usuários específicos sobre para quem a política de usuário é atribuída. Por exemplo, se você habilitar o acesso de usuário remoto na política global e local, você pode especificar uma política de usuário que desabilita o acesso do usuário remoto e atribui essa política de usuário para usuários específicos. Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que tenha efeito.

Para determinar quais definições de configurações e quais políticas você precisa criar ou editar, consulte os seguintes pontos de decisão:

**Deseja permitir que usuários internos e externos do seu domínio possam colaborar usando mensagem instantânea, conferência da Web e Áudio/Vídeo?**

Configure as configurações conforme detalhado nos tópicos Configure policies to control [remote usercces](external-access-policies/configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Deseja permitir que usuários anônimos participem e sejam convidados para conferências hospedadas por usuários em sua implantação?**

Configurar as configurações conforme detalhado no tópico Atribuir políticas de conferência para dar suporte a [usuários anônimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) e [Criar políticas de conferência.](../conferencing/create-policies.md)

**Deseja permitir que os usuários se comuniquem com contatos do Domínio Federado SIP?**

Configure as configurações conforme detalhado nos tópicos Configure policies to control [federated](external-access-policies/configure-policies-to-control-federated-user-access.md)user access , Enable or disable federation and [public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), and [Manage SIP federated domains for your organization](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Se você habilitar a comunicação com domínios federados SIP, deseja habilitar a descoberta automática da Federação SIP?**

Configure as configurações conforme detalhado no tópico [Habilitar ou desabilitar a descoberta de parceiros de federação.](access-edge/enable-or-disable-discovery-of-federation-partners.md)

**Se você habilitou a comunicação com Domínios Federados SIP, você não desejam habilitar o envio de uma declaração para contatos Federados notificando-os que você usa o arquivamento e as comunicações podem ser arquivadas?**

Configure as configurações conforme detalhado no tópico Habilitar ou desabilitar o envio de um aviso de [isenção](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)de responsabilidade de arquivamento para parceiros federados em .

**Você deseja permitir que os usuários se comuniquem com Provedores Federados SIP que habilitam a comunicação com provedores públicos?**

Configurar as configurações conforme detalhado nos tópicos Configure policies to control [public user access](external-access-policies/configure-policies-to-control-public-user-access.md), Enable or disable federation and public [IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit public SIP federated providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Você deseja permitir que os usuários se comuniquem com provedores federados SIP que sejam provedores hospedados executando Microsoft 365 ou Office 365 e Skype for Business Online?**

Configure as configurações conforme detalhado nos tópicos Habilitar ou desabilitar a conectividade de [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) pública e federação e Criar ou editar provedores [federados SIP hospedados.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)

**Sua implantação está configurada em um domínio dividido (também conhecido como híbrido), onde alguns usuários possuem seus servidor inicial em uma implantação local e outros usuários configurados com um servidor inicial em um ambiente online?**

Configure as configurações conforme detalhado nos tópicos Configure policies to control [federated](external-access-policies/configure-policies-to-control-federated-user-access.md)user access , Enable or disable federation and [public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), and [Create or edit hosted SIP federated providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


É possível definir configurações de acesso de usuário externo, incluindo qualquer política que deseja usar para controlar o acesso de usuário externo, mesmo se não habilitou o acesso de usuário externo para sua organização. No entanto, as políticas e outras configurações definidas entram em vigor apenas quando você habilitou acesso de usuário externo para sua organização. Os usuários externos não podem se comunicar com os usuários da sua organização quando o acesso de usuário externo está desabilitado ou se nenhuma política de acesso do usuário externo está configurada para suporá-lo.

Sua implantação de borda autentica os tipos de usuário externos (exceto usuários anônimos que são autenticados pelo ID da conferência e uma chave de passe enviada ao participante anônimo ao criar a conferência e convidar os participantes) e controla o acesso com base em como você configura seu suporte de borda. Para poder controlar as comunicações, é possível configurar uma ou mais políticas e definir outras configurações que definem como os usuários dentro e fora da sua implantação se comunicam entre si. As políticas e configurações incluem a política global padrão para acesso de usuário externo, além de políticas local e do usuário que podem ser criadas e configuradas para habilitar um ou mais tipos de acesso de usuário externo para locais ou usuários específicos.

