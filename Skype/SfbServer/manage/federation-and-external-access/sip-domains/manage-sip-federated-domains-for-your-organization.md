---
title: Gerenciar domínios SIP federados para sua organização
ms.reviewer: ''
ms:assetid: abc48829-e5cf-4651-bc38-899192f5c3bc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552454(v=OCS.15)
ms:contentKeyID: 48679565
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
description: Saiba como gerenciar e configurar domínios SIP com os quais você pode federar,
ms.openlocfilehash: 7b04225542387d52a36533c9639b02f773731e9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817211"
---
# <a name="manage-sip-federated-domains-for-your-organization-in-skype-for-business-server"></a>Gerenciar domínios sip federados para sua organização no Skype for Business Server


Para gerenciar e configurar domínios SIP com os quais você pode federar, siga o seguinte procedimento:

  - Crie ou edite uma lista de domínios permitidos de domínios parceiros federados SIP.

  - Crie ou edite uma lista de domínios bloqueados de domínios federados SIP.

## <a name="configure-support-for-allowed-external-domains-in-skype-for-business-server"></a>Configurar suporte para domínios externos permitidos no Skype for Business Server

Se você configurou suporte para parceiros federados, você pode gerenciar quais domínios federar com a sua organização. Você configura um ou mais domínios externos específicos como domínios federados permitidos. Para fazer isso, adicione cada domínio à lista de domínios permitidos. Mesmo se a descoberta de parceiro estiver habilitada para sua organização, faça isso se o domínio for um parceiro federado que talvez precise se comunicar com mais de 1.000 usuários ou talvez precise enviar mais de 20 mensagens por segundo. Se a descoberta de parceiro não estiver habilitada para a sua organização, somente os usuários de domínios externos que você adiciona à lista de domínios permitidos podem participar em conferência e mensagens instantâneas com usuários em sua organização. Se você quiser restringir o acesso de um domínio federado a um servidor específico que executa o serviço de Borda de Acesso do parceiro federado, poderá especificar o nome de domínio do servidor que executa o serviço de Borda de Acesso para cada domínio na lista de domínios permitidos.

> [!NOTE]  
> Este procedimento descreve como configurar o suporte para domínios específicos, mas implementar suporte para usuários federados também exige que você habilite o suporte para usuários federados de sua organização, bem como configure e aplique políticas para controlar quais usuários podem colaborar com usuários federados. Para obter detalhes sobre como habilitar o suporte para usuários federados, consulte [Habilitar ou desabilitar o acesso de usuário remoto.](../access-edge/enable-or-disable-remote-user-access.md) Para obter detalhes sobre como configurar políticas para controlar a federação, consulte Configurar políticas [para controlar o acesso de usuário federado.](../external-access-policies/configure-policies-to-control-federated-user-access.md)

### <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para adicionar um domínio externo à lista de domínios permitidos

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.
2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
3.  Na barra de navegação esquerda, clique em **Acesso de Usuário Externo** e em **Domínios Federados**.
4.  Na página **Domínios Federados**, clique em **Novo** e em **Domínio permitido**.
5.  Em **Novos Domínios Federados**, faça o seguinte:
    
      - Em **Nome de domínio (ou FQDN)**, digite o nome do domínio do parceiro federado.       

        > [!NOTE]  
        > Esse nome deve ser exclusivo e não pode já existir como um domínio permitido para este servidor que executa o serviço de Borda de Acesso. O nome não pode exceder 256 caracteres.<BR><br>A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar **contoso.com**, a pesquisa também retornará o domínio **it.contoso.com**.<BR><br>Um domínio de parceiro federado não pode ser simultaneamente bloqueado e permitido. O Skype for Business Server impede que isso aconteça para que você não tenha que sincronizar suas listas.
    
      - Se você quiser restringir o acesso para esse domínio federado a usuários de um servidor específico que execute o serviço de Borda de Acesso, em **Serviço de Borda de Acesso (FQDN)**, digite o FQDN do servidor do domínio federado executando o serviço de Borda de Acesso.    
      - Se você quiser fornecer informações adicionais, em **Comentário**, digite as informações que deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.
7.  Repita as etapas 4 a 6 para cada domínio de parceiro federado que deseja permitir.

Para habilitar o acesso de usuário federado, habilite também o suporte para acesso de usuário federado em sua organização. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto.](../access-edge/enable-or-disable-remote-user-access.md)

Além disso, você deve configurar e aplicar a política a usuários que possam colaborar com usuários federados. Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário federado.](../external-access-policies/configure-policies-to-control-federated-user-access.md)

## <a name="configure-support-for-blocked-external-domains-in-skype-for-business-server"></a>Configurar suporte para domínios externos bloqueados no Skype for Business Server 

Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios serão impedidos de federar com sua organização. A lista de domínios bloqueados atuará como uma lista de bloqueios (listagem de entradas explícitas que não devem ser permitidas) e será aplicada na descoberta de domínio federado, se você tiver essa opção habilitada. Para obter detalhes, consulte [Habilitar ou desabilitar a descoberta de parceiros de federação.](../access-edge/enable-or-disable-discovery-of-federation-partners.md)

Impedir que um ou mais domínios externos se conectem à sua organização. Para fazer isso, adicione o domínio à lista de domínios bloqueados.


### <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para adicionar um domínio externo à lista de domínios bloqueados

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.
2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
3.  Na barra de navegação esquerda, clique em **Acesso de Usuário Externo**.
4.  Clique **em Domínios Federados,** clique em **Novo** e em **Domínio Bloqueado.**
5.  Em **Novos Domínios Federados**, faça o seguinte:
    
      - Em **Nome de domínio (ou FQDN),** digite o nome do domínio do parceiro federado que você deseja bloquear.

        > [!NOTE]  
        > O nome não pode exceder 256 caracteres.<BR><br>A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar **contoso.com**, a pesquisa também retornará o domínio **it.contoso.com**.<BR><br>Um domínio de parceiro federado não pode ser simultaneamente bloqueado e permitido. O Skype for Business Server impede que isso aconteça para que você não tenha que sincronizar suas listas.
   
      - (Opcional) Em **Comentário,** digite informações que você deseja compartilhar com outros administradores do sistema sobre essa configuração.

6.  Clique em **Confirmar**.
7.  Repita as etapas 4 a 6 para cada parceiro federado que você deseja bloquear.

Para habilitar o acesso de usuário federado, habilite também o suporte para acesso de usuário federado em sua organização. Para obter detalhes, consulte [Habilitar ou desabilitar o acesso de usuário remoto.](../access-edge/enable-or-disable-remote-user-access.md)

Além disso, você deve configurar e aplicar a política a usuários que possam colaborar com usuários federados. Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário federado.](../external-access-policies/configure-policies-to-control-federated-user-access.md)


## <a name="see-also"></a>Confira também

[Configurar políticas para controlar acesso de usuário federado](../external-access-policies/configure-policies-to-control-federated-user-access.md)  

[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

[Habilitar ou desabilitar descoberta de parceiros de federação](../access-edge/enable-or-disable-discovery-of-federation-partners.md)
  

