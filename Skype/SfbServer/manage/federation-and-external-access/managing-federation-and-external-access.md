---
title: 'Lync Server 2013: Gerenciando federação e acesso externo ao Skype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você habilita e configura o acesso de usuário externo para controlar se os usuários externos suportados podem colaborar com usuários internos do Skype for Business Server.
ms.openlocfilehash: df8ca25dcaffb9ee563691eb327dc9ea6e9a229c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826601"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gerenciando federação e acesso externo ao Skype for Business Server

Implantar um Servidor de borda ou um pool de Borda é a primeira etapa para suportar usuários externos. Para obter detalhes sobre como implantar Servidores de Borda, [consulte Deploy Edge Server in Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Depois de instalar e configurar sua implantação interna do Skype for Business Server, os usuários internos em sua organização podem colaborar com outros usuários internos que possuem contas SIP em seus Serviços de Domínio do Active Directory (AD DS). A colaboração pode incluir o envio e recebimento de mensagens instantâneas e a atualização do status de presença e participação nas conferências (também conhecido como "reuniões). Você habilita e configura o acesso de usuário externo para controlar se os usuários externos suportados podem colaborar com usuários internos do Skype for Business Server. Os usuários externos podem incluir usuários remotos de sua implantação, usuários federados (incluindo usuários com suporte de provedores de serviços públicos de mensagens instantâneas (IM) e participantes anônimos em conferências.

Se sua implantação incluiu a instalação de um Servidor de Borda do Skype for Business Server ou de um pool de Borda, o escopo de possíveis tipos de comunicação é bastante expandido com várias opções de acesso de usuário externo, comunicação com membros de outros domínios federados SIP e provedores federados SIP. Depois de configurar o Servidor de Borda ou pool de Borda, você habilita os tipos de acesso de usuário externo que deseja fornecer e configura as políticas para controlar o acesso externo. No Skype for Business Server, você habilita e configura o acesso de usuário externo e as políticas usando o Painel de Controle do Skype for Business Server, o Shell de Gerenciamento do [Skype for Business Server](../management-shell.md)ou ambos, com base nos requisitos da tarefa. 



> [!IMPORTANT]  
> Ao projetar sua configuração e políticas para acesso do usuário externo, você deve compreender a precedência das políticas e como as políticas são aplicadas. As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.


Por padrão, nenhuma política está configurada para oferecer suporte ao acesso de usuários externos, incluindo acesso de usuários remotos, acesso de usuários federados, mesmo se você já tiver habilitado o suporte ao acesso de usuários externos na sua organização. Para controlar o uso do acesso de usuários externos, configure uma ou mais políticas, especificando o tipo de acesso de usuários externos com suporte para cada política. Isso inclui as seguintes políticas de acesso externo:

  - **Política global**   A política global é criada quando você implanta seus Servidores de Borda. Por padrão, nenhuma opção de acesso do usuário externo está habilitada na política global. Para suportar o acesso do usuário externo a nível global, você deve configurar a política global para suportar um ou mais tipos de opções de acesso do usuário externo. A política global se aplica a todos os usuários na sua organização, mas as políticas locais e as políticas de usuário substituem a política global. Ao excluir a política global, ela não é removida. Ao invés, é redefinida para a configuração padrão.

  - **Política de site**   Você pode criar e configurar uma ou mais políticas de site para limitar o suporte ao acesso de usuários externos a sites específicos. A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política. Por exemplo, se você ativar o acesso de usuário remoto na política global, pode especificar uma política de local que o desative para um local específico. Por padrão, a política de local é aplicada a todos os usuários do local, mas você pode atribuir uma política de usuário para substituir a configuração da política de local.

  - **Política de usuário**   Você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte ao acesso de usuário remoto a usuários específicos. A configuração da política de usuário substitui a política global e a do local, mas apenas para usuários específicos aos quais a política de usuário é atribuída. Por exemplo, se você ativar o acesso de usuário remoto na política global e na de local, deve especificar uma política de usuário que a desative e depois atribuir essa política de usuário a usuários específicos. Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que ela surta efeito.

Para determinar quais definições de configurações e quais políticas você precisa criar ou editar, consulte os seguintes pontos de decisão:

**Deseja permitir que usuários internos e externos do seu domínio possam colaborar usando mensagem instantânea, conferência da Web e Áudio/Vídeo?**

Definir as configurações conforme detalhado nos tópicos Configurar políticas para controlar [o](external-access-policies/configure-policies-to-control-remote-user-access.md)acesso de usuário remoto e Habilitar ou desabilitar federação e conectividade pública de [IM.](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

**Deseja permitir que usuários anônimos participem e sejam convidados para conferências hospedadas por usuários em sua implantação?**

Defina as configurações conforme detalhado no tópico Atribuir políticas de conferência para dar suporte a usuários [anônimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) e [Criar políticas de conferência.](../conferencing/create-policies.md)

**Deseja permitir que os usuários se comuniquem com contatos do Domínio Federado SIP?**

Configure as configurações, conforme detalhado nos tópicos Configurar políticas para controlar o acesso de usuário [federado,](external-access-policies/configure-policies-to-control-federated-user-access.md)habilitar ou desabilitar federação e conectividade de [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)pública e gerenciar [domínios sip federados](sip-domains/manage-sip-federated-domains-for-your-organization.md)para sua organização.


**Se você habilitar a comunicação com Domínios Federados SIP, deseja habilitar a descoberta automática da Federação SIP?**

Definir as configurações conforme detalhado no tópico [Habilitar ou desabilitar a descoberta de parceiros de federação.](access-edge/enable-or-disable-discovery-of-federation-partners.md)

**Se você habilitou a comunicação com Domínios Federados SIP, você não desejam habilitar o envio de uma declaração para contatos Federados notificando-os que você usa o arquivamento e as comunicações podem ser arquivadas?**

Definir as configurações conforme detalhado no tópico Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento para parceiros [federados em](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Deseja permitir que os usuários se comuniquem com Provedores Federados SIP que permitem a comunicação com provedores públicos?**

Definir as configurações, conforme detalhado nos [tópicos](external-access-policies/configure-policies-to-control-public-user-access.md)Configurar políticas para controlar o acesso de usuário público, habilitar ou desabilitar federação e conectividade pública de [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)e Criar ou editar provedores [sip públicos federados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Deseja permitir que os usuários se comuniquem com Provedores Federados SIP hospedados executando o Microsoft 365 ou Office 365 e o Skype for Business Online?**

Configure as configurações conforme detalhado nos tópicos Habilitar ou desabilitar a federação e a conectividade de [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) pública e Criar ou editar provedores [federados SIP hospedados.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)

**Sua implantação está configurada em um domínio dividido (também conhecido como híbrido), onde alguns usuários possuem seus servidor inicial em uma implantação local e outros usuários configurados com um servidor inicial em um ambiente online?**

Definir as configurações, conforme detalhado nos tópicos Configurar políticas para controlar o acesso de usuário [federado,](external-access-policies/configure-policies-to-control-federated-user-access.md)habilitar ou desabilitar federação e conectividade de [IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)pública e Criar ou editar provedores [federados SIP hospedados.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)


É possível definir configurações de acesso de usuário externo, incluindo qualquer política que deseja usar para controlar o acesso de usuário externo, mesmo se não habilitou o acesso de usuário externo para sua organização. No entanto, as políticas e outras configurações definidas entram em vigor apenas quando você habilitou acesso de usuário externo para sua organização. Os usuários externos não podem se comunicar com os usuários da sua organização quando o acesso de usuário externo está desabilitado ou se nenhuma política de acesso do usuário externo está configurada para suporá-lo.

Sua implantação de borda autentica os tipos de usuário externos (exceto usuários anônimos que são autenticados pelo ID da conferência e uma chave de passe enviada ao participante anônimo ao criar a conferência e convidar os participantes) e controla o acesso com base em como você configura seu suporte de borda. Para poder controlar as comunicações, é possível configurar uma ou mais políticas e definir outras configurações que definem como os usuários dentro e fora da sua implantação se comunicam entre si. As políticas e configurações incluem a política global padrão para acesso de usuário externo, além de políticas local e do usuário que podem ser criadas e configuradas para habilitar um ou mais tipos de acesso de usuário externo para locais ou usuários específicos.

