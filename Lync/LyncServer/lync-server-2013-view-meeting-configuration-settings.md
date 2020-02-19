---
title: 'Lync Server 2013: Exibir definições de configuração de reunião'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac2af6e82546e44e0d10084e5878cef0e1a6b6f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Exibir definições de configuração de reunião no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

No painel de controle do Lync Server 2013, você usa a configuração de reunião para controlar como as reuniões são implementadas em sua implantação. Isto inclui a seguintes configurações de reunião:

  - Uma configuração global criada por padrão ao implantar o Lync Server 2013.

  - Configurações a nível do usuário ou do site opcionais que você cria e usa para especificar como as reuniões são implementadas para sites ou usuários específicos.

<div>

## <a name="to-view-meeting-configuration-settings"></a>Para exibir configurações de reunião

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Conferência** e em **Configuração da reunião**.

4.  Na página **Configuração de Reunião**, clique na configuração de reunião que você deseja exibir.

5.  Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar detalhes...**.
    
    **Editar configuração de reunião \<-\> a política** abre exibindo as configurações da política selecionada. Para obter detalhes sobre como definir as configurações, consulte [create or Modify a Collection of Meeting Configuration Settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de configuração de reunião usando os cmdlets do Windows PowerShell

As definições de configuração de reunião podem ser exibidas usando o Windows PowerShell e o cmdlet Get-CsMeetingConfiguration. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-view-meeting-configuration-information"></a>Para exibir informações de configuração de reunião

  - Para exibir informações sobre todas as suas definições de configuração de reunião, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsMeetingConfiguration
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

