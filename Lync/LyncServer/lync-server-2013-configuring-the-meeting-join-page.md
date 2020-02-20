---
title: 'Lync Server 2013: Configurando a página de ingresso na reunião'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 977903d8d85b3eaa4d944e8b3e62ec0df629c1d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Configurando a página de ingresso na reunião no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-14_

Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário. Se um cliente já estiver instalado, ele abre e participa da reunião. Se um cliente não estiver instalado, por padrão, a versão 2013 do Lync Web App é aberta.

Você pode modificar o comportamento da página de ingresso na reunião se quiser permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant. Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet Set-CsWebServiceConfiguration.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Parâmetros do Set-CsWebServiceConfiguration da página de participação de reunião

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parâmetro Set-CsWebServiceConfiguration</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Se for definido como true, os usuários que ingressarem em uma reunião usando um aplicativo cliente que não seja o Lync serão considerados a oportunidade de participar da reunião usando o Office Communicator 2007 R2. O valor padrão é False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Quando for definido como True, as opções alternativas para ingresso em uma conferência online (como Office Communicator 2007 R2) serão automaticamente expandidas e exibidas aos usuários. Quando for definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções por conta própria.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Para configurar a página de ingresso na reunião usando o Shell de gerenciamento do Lync Server 2013

1.  Inicie o Shell de gerenciamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.

2.  Para visualizar as definições de configuração do serviço da web, execute o seguinte cmdlet:
    
        Get-CsWebServiceConfiguration

3.  Execute o comando a seguir, com os parâmetros definidos como true ou false, dependendo da sua preferência (para obter detalhes sobre os parâmetros desse cmdlet, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) na documentação do Shell de gerenciamento do Lync Server 2013:
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>Confira também


[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

