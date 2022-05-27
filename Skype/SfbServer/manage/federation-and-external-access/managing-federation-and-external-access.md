---
title: 'Lync Server 2013: Gerenciando federação e acesso externo ao Skype for Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você habilita e configura o acesso de usuário externo para controlar se os usuários externos com suporte podem colaborar com Skype for Business Server usuários internos.
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676213"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gerenciando federação e acesso externo ao Skype for Business Server

Implantar um Servidor de borda ou um pool de Borda é a primeira etapa para suportar usuários externos. Para obter detalhes sobre como implantar servidores de borda, [consulte Implantar o Servidor de Borda Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Depois de instalar e configurar sua implantação interna do Skype for Business Server, os usuários internos em sua organização podem colaborar com outros usuários internos que têm contas SIP em seu Active Directory Domain Services (AD DS). A colaboração pode incluir o envio e recebimento de mensagens instantâneas e a atualização do status de presença e participação nas conferências (também conhecido como "reuniões). Você habilita e configura o acesso de usuário externo para controlar se os usuários externos com suporte podem colaborar com Skype for Business Server usuários internos. Os usuários externos podem incluir usuários remotos de sua implantação, usuários federados (incluindo usuários com suporte de provedores de serviços de mensagens instantâneas públicas) e participantes anônimos em conferências.

Se sua implantação incluir um Skype for Business Server Edge Server ou um pool de Borda, o escopo de possíveis tipos de comunicação será muito expandido. Há muitas opções para acesso de usuário externo, comunicação com membros de outros domínios federados SIP e provedores federados SIP. Depois de configurar o pool do Servidor de Borda ou do Edge, você habilita os tipos de acesso de usuário externo e configura políticas para controlar o acesso externo. No Skype for Business Server, você habilita e configura políticas e acesso de usuário externo usando o Skype for Business Server Painel de Controle, o Shell de Gerenciamento Skype for Business Server [ou](../management-shell.md) ambos.

> [!IMPORTANT]
> Ao projetar sua configuração e políticas para acesso do usuário externo, você deve compreender a precedência das políticas e como as políticas são aplicadas. Skype for Business Server configurações de política aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.

Por padrão, nenhuma política dá suporte ao acesso de usuário externo (incluindo acesso de usuário remoto e acesso de usuário federado), mesmo que você já tenha habilitado o suporte de acesso de usuário externo para sua organização. Para controlar o uso do acesso de usuário externo, você deve configurar uma ou mais políticas. Nas políticas a seguir, você especifica o tipo de acesso de usuário externo com suporte:

- **Política global**: a política global é criada quando você implanta seus Servidores de Borda. Por padrão, nenhuma opção de acesso do usuário externo está habilitada na política global. Para dar suporte ao acesso de usuário externo no nível global, configure a política global para dar suporte a um ou mais tipos de acesso de usuário externo. A política global se aplica a todos os usuários na sua organização, mas as políticas locais e as políticas de usuário substituem a política global. Ao excluir a política global, ela não é removida. Ao invés, é redefinida para a configuração padrão.

- **Política de** site: você pode criar e configurar uma ou mais políticas de site para limitar o suporte para acesso de usuário externo a sites específicos. A configuração na política de site substitui a política global, mas somente para o site específico coberto pela política de site. Por padrão, uma política de site é aplicada a todos os usuários nesse site, mas políticas de usuário para substituir as configurações de política de site.

- **Política de usuário**: você pode criar e configurar uma ou mais políticas de usuário para limitar o suporte ao acesso de usuário remoto a usuários específicos. A configuração na política de usuário substitui a política global e do site, mas somente para os usuários específicos aos quais a política é atribuída. Se você criar uma política de usuário, deve aplicá-la a um ou mais usuários antes que tenha efeito.

Para determinar quais definições de configurações e quais políticas você precisa criar ou editar, consulte os seguintes pontos de decisão:

**Deseja permitir que usuários internos e externos do seu domínio possam colaborar usando mensagem instantânea, conferência da Web e Áudio/Vídeo?**

Defina as configurações conforme detalhado nos [tópicos Configurar](external-access-policies/configure-policies-to-control-remote-user-access.md) políticas para controlar o acesso de usuário remoto e habilitar ou desabilitar a federação e a conectividade [de mensagens instantâneas públicas](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Deseja permitir que usuários anônimos participem e sejam convidados para conferências hospedadas por usuários em sua implantação?**

Defina as configurações conforme detalhado no tópico Atribuir políticas de conferência para dar suporte [a usuários anônimos](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) e [criar políticas de conferência](../conferencing/create-policies.md).

**Deseja permitir que os usuários se comuniquem com contatos do Domínio Federado SIP?**

Defina as configurações conforme detalhado nos tópicos Configurar políticas para controlar o acesso de usuário [federado](external-access-policies/configure-policies-to-control-federated-user-access.md), habilitar ou desabilitar a federação e a conectividade de [mensagens](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) [instantâneas públicas e gerenciar domínios federados SIP](sip-domains/manage-sip-federated-domains-for-your-organization.md) para sua organização.

**Se você habilitou a comunicação com domínios federados SIP, deseja habilitar a descoberta automática da Federação SIP?**

Defina as configurações conforme detalhado no tópico Habilitar [ou desabilitar a descoberta de parceiros de federação](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Se você habilitou a comunicação com Domínios Federados SIP, você não desejam habilitar o envio de uma declaração para contatos Federados notificando-os que você usa o arquivamento e as comunicações podem ser arquivadas?**

Defina as configurações conforme detalhado no tópico Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de arquivamento para parceiros [federados](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Deseja permitir que os usuários se comuniquem com provedores federados SIP que habilitem a comunicação com provedores públicos?**

Defina as configurações conforme detalhado nos [tópicos Configurar](external-access-policies/configure-policies-to-control-public-user-access.md) políticas para controlar o acesso do usuário público, habilitar ou desabilitar a federação e a conectividade de [mensagens](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) instantâneas públicas e criar ou editar provedores [federados SIP públicos](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)

**Deseja permitir que os usuários se comuniquem com provedores federados SIP que são provedores hospedados que executam o Microsoft 365 ou Office 365 e Skype for Business Online?**

Defina as configurações conforme detalhado nos tópicos Habilitar ou desabilitar a federação e a conectividade de [mensagens](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) instantâneas públicas e criar ou editar provedores [federados SIP hospedados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Sua implantação está configurada em um domínio dividido (também conhecido como híbrido), onde alguns usuários possuem seus servidor inicial em uma implantação local e outros usuários configurados com um servidor inicial em um ambiente online?**

Defina as configurações conforme detalhado nos tópicos Configurar políticas para controlar o acesso de usuário [federado](external-access-policies/configure-policies-to-control-federated-user-access.md), habilitar ou desabilitar a federação e a conectividade de [mensagens](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) instantâneas públicas e criar ou editar provedores [federados SIP hospedados](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

Você pode definir configurações de acesso de usuário externo mesmo se não tiver habilitado o acesso de usuário externo para sua organização. No entanto, as políticas e outras configurações definidas entram em vigor apenas quando você habilitou acesso de usuário externo para sua organização. Os usuários externos não poderão se comunicar com seus usuários quando o acesso de usuário externo estiver desabilitado ou se nenhuma política de acesso de usuário externo estiver configurada para dar suporte a ele.

Sua implantação de borda autentica os tipos de usuários externos e controla o acesso com base em como você configura o suporte de borda. A exceção a essa regra são usuários anônimos, que são autenticados pela ID de conferência e uma chave de acesso que é enviada ao participante anônimo quando você cria a conferência e convida os participantes. Para controlar a comunicação, você pode configurar uma ou mais políticas que definem como os usuários dentro e fora de sua organização se comunicam entre si. As políticas e configurações incluem a política global padrão, as políticas de site e as políticas de usuário que você pode criar e configurar.
