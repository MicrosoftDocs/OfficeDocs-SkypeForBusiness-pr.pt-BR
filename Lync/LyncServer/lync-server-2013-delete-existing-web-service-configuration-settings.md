---
title: 'Lync Server 2013: excluir configurações de configuração de serviço Web existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb310836e78d46f94412018f3034a4a5f7d7173
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Excluir as configurações de configuração de serviço Web existentes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Siga estas etapas para excluir definições de configuração do serviço da web.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>Para excluir definições de configuração de serviço da Web

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.

4.  Na página **Serviço da Web**, e no campo de pesquisa, digite todo ou parte do nome da política que você deseja excluir.

5.  Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.

6.  Clique em **OK**.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Excluindo configurações de serviço Web usando cmdlets do Windows PowerShell

Você pode excluir as configurações de serviço Web usando o Windows PowerShell e o cmdlet **Remove-CsWebServiceConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Para excluir um conjunto específico de definições de configuração do serviço da Web

  - O seguinte comando remove as configurações de segurança do Serviço da Web aplicadas ao local Redmond:
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Para excluir todas as definições de configuração do serviço da Web aplicadas ao escopo local

  - O seguinte comando remove todas as configurações de segurança do Serviço da Web aplicadas ao escopo do serviço:
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Para excluir todas as definições de configuração do Serviço da Web que permitem a autenticação de certificado

  - O seguinte comando remove todas as configurações de segurança do Serviço da Web que permitem o uso de autenticação de certificados:
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

Para obter detalhes, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando autenticação no painel de controle do Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

