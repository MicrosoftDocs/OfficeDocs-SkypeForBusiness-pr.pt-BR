---
title: Configurar o acesso de convidados no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: Habilite o recurso do acesso de convidados no Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a>Configurar o acesso de convidados no Microsoft Teams
======================================

O Microsoft Teams é construído em cima dos grupos do Office 365 e também depende do SharePoint Online. É por isso que as configurações específicas devem ser habilitadas nos Grupos do Office 365 e no SharePoint Online, além de ativar o recurso de acesso de convidado no Teams.


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a>Permitir a adição de convidados nos grupos do Office 365
<a name="bkmk_ControlAddingGuestUsers"> </a>


1. Inicie sessão na sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.
    
  
3. Selecione **Grupos do Office 365**.
    
     ![Grupos do Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. Na página de grupos do Office 365, selecione o botão de alternância para **Habilitar** ou **Desabilitar**, dependendo se desejar permitir que os proprietários de equipes e de grupos de fora de sua organização acessem os grupos do Office 365. Clique ou toque no botão de alternância para **Habilitar** ao lado de **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**.


![A captura de tela mostra o painel de Grupos do Office 365 com as opções habilitadas para permitir que membros de grupo de fora da organização acessem o conteúdo do grupo e para permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a>Habilitar o compartilhamento no SharePoint Online

A opção de compartilhamento no SharePoint Online permite que convidados sejam adicionados à sua organização. Por padrão, a opção de compartilhamento está habilitada. Para obter informações sobre como desabilitar a opção de compartilhamento, consulte [Desabilitar a opção de compartilhamento](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).
  
   Os administradores podem criar contas de convidados no Azure Active Directory, independentemente das configurações de compartilhamento externo. Se o compartilhamento externo estiver desativado, somente um administrador pode criar contas de convidados. 
    

> [!IMPORTANT]
> Se você desabilitar a opção de compartilhamento, o acesso de convidados ficará indisponível. 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Habilitar ou desabilitar o acesso de convidados no Microsoft Teams
<a name="bkmk_TurnonOrTurnOff"> </a>

Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados. 

As configurações do convidado são definidas no Azure Active Directory. Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365. Se um usuário vir a mensagem “Entre em contato com o seu administrador” ao tentar adicionar um convidado para a sua equipe, aparentemente o recurso de convidados não foi habilitado ou as configurações ainda não entraram em vigor.



1. Inicie sessão na sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.
    
     ![Inicie sessão no Office 365, vá para o centro de administração, vá até Configurações, e então escolha Serviços &amp; complementos.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. Selecione **Microsoft Teams**.
    
     ![A captura de tela mostra a opção para o complemento do Microsoft Teams, conforme selecionado do centro de administração do Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. Em **Selecionar o tipo de licença/usuário que deseja configurar**, selecione **Convidado**.
   
    ![A captura de tela do complemento do Microsoft Teams mostra a licença de Convidado selecionada e a opção do Microsoft Teams definida para Habilitado.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. Clique ou toque no botão de alternância ao lado de **Tornar o Microsoft Teams habilitado ou desabilitado para todos os usuários desse tipo** para **Habilitar** para ativar o acesso de convidados no Teams para a sua organização e, em seguida, escolha **Salvar**. 
    
  

