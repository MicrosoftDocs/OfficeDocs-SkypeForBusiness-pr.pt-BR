---
title: Gerenciar domínios SIP federados para sua organização
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba como gerenciar e configurar domínios SIP que você pode federar
ms.openlocfilehash: aa793c5380c4baaa18876bfa2e2891a8260670dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903170"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gerenciar domínios federados SIP para sua organização no Skype para Business Server


Para gerenciar e configurar domínios SIP que você pode federar, você pode fazer o seguinte:

  - Crie ou edite uma lista de domínios permitidos de domínios de parceiros federados SIP.

  - Crie ou edite uma lista de domínios bloqueados de domínios federados SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurar o suporte a domínios externos permitidos no Skype para Business Server

Se você tiver configurado o suporte para parceiros federados, é possível gerenciar quais domínios específicos poderão se federar à sua organização. Você pode configurar um ou mais domínios externos específicos como domínios federados permitidos. Para fazer isso, adicione cada domínio à lista de domínios permitidos. Mesmo se a descoberta de parceiros estiver habilitada para sua organização, fazer isso se o domínio é um parceiro federado que talvez seja necessário se comunicar com mais de 1.000 dos usuários ou pode precisar enviar mais de 20 mensagens por segundo. Se a descoberta de parceiros não estiver habilitada para a sua organização, somente os usuários de domínios externos que você adicionar à lista de domínios permitidos podem participar de IM e conferência com usuários em sua organização. Se você deseja restringir o acesso de um domínio federado para um servidor específico que executa o serviço de borda de acesso do parceiro federado, você poderá especificar o nome de domínio do servidor que executa o serviço de borda de acesso para cada domínio na lista de domínios permitidos.

> [!NOTE]  
> Este procedimento descreve como configurar o suporte para domínios específicos, mas a implementação de suporte para os usuários federados também requer que você habilitar o suporte para os usuários federados da sua organização, configurar e aplica políticas para controlar quais usuários podem Colabore com usuários federados. Para obter detalhes sobre como habilitar o suporte a usuários federados, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md). Para obter detalhes sobre como configurar políticas para controlar a federação, consulte [Configure políticas para controlar federados acesso de usuário](../external-access-policies/configure-policies-to-control-federated-user-access.md).

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para adicionar um domínio externo à lista de domínios permitidos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Domínios federados**.
4.  Na página **Domínios federados** , clique em **novo**e, em seguida, clique em **domínio permitido**.
5.  Em **Novos domínios federados**, faça o seguinte:
    
      - Em **nome de domínio (ou FQDN)**, digite o nome do domínio do parceiro federado.       

        > [!NOTE]  
        > Esse nome deve ser exclusivo e não pode já existir como um domínio permitido para o servidor que executa o serviço de borda de acesso. O nome não pode exceder 256 caracteres de comprimento.<BR><br>A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar **contoso.com**, a pesquisa também retornará o domínio **it.contoso.com**.<BR><br>Um domínio de parceiro federado simultaneamente não pode ser bloqueado e permitido. Skype para Business Server impede que isso acontecendo para que você não tiver a sincronização de suas listas.
    
      - Se você deseja restringir o acesso para este domínio federado para usuários de um servidor específico executando o serviço de borda de acesso, no **serviço de borda de acesso (FQDN)**, digite o FQDN do servidor do domínio federado executando o serviço de borda de acesso.    
      - Se você quiser fornecer informações adicionais, em **comentário**, digite as informações que você deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.
7.  Repita as etapas 4 a 6 para cada domínio de parceiro federado que você deseja permitir.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para acesso de usuário federado na sua organização. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política aos usuários que você deseja pudessem colaborar com usuários federados. Para obter detalhes, consulte [Configure políticas para controlar federados acesso de usuário](../external-access-policies/configure-policies-to-control-federated-user-access.md).

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurar o suporte a domínios externos bloqueados no Skype para Business Server 

Se você tiver configurado o suporte para parceiros federados, é possível gerenciar quais domínios serão bloqueados de se federar a sua organização. A lista de domínios bloqueados irão agir como uma lista de bloqueios (listagem das entradas explícitas que não devem ser permitidas) e será aplicada a descoberta de domínio federado, se você tiver esta opção ativada. Para obter detalhes, consulte [Habilitar ou desabilitar a descoberta de parceiros de Federação](../access-edge/enable-or-disable-discovery-of-federation-partners.md).

Bloquear um ou mais domínios externos de se conectar à sua organização. Para fazer isso, adicione o domínio à lista de domínios bloqueados.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para adicionar um domínio externo à lista de domínios bloqueados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**.
4.  Clique em **Domínios federados**, clique em **novo**e, em seguida, clique em **domínio bloqueado**.
5.  Em **Novos domínios federados**, faça o seguinte:
    
      - Em **nome de domínio (ou FQDN)**, digite o nome do domínio de parceiro federado que deseja bloquear.

        > [!NOTE]  
        > O nome não pode exceder 256 caracteres de comprimento.<BR><br>A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar **contoso.com**, a pesquisa também retornará o domínio **it.contoso.com**.<BR><br>Um domínio de parceiro federado simultaneamente não pode ser bloqueado e permitido. Skype para Business Server impede que isso acontecendo para que você não tiver a sincronização de suas listas.
   
      - (Opcional) Em **comentário**, digite as informações que você deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.
7.  Repita as etapas 4 a 6 para cada parceiro federado que deseja bloquear.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para acesso de usuário federado na sua organização. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política aos usuários que você deseja pudessem colaborar com usuários federados. Para obter detalhes, consulte [Configure políticas para controlar federados acesso de usuário](../external-access-policies/configure-policies-to-control-federated-user-access.md).


## <a name="see-also"></a>Confira também

[Configurar políticas para controlar acesso de usuário federado](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Habilitar ou desabilitar descoberta de parceiros de federação](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

