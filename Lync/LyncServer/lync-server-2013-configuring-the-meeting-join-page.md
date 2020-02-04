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
ms.openlocfilehash: 8471b6b897a365763d55edcbd55e4a9bab4a3124
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Configurando a página de ingresso na reunião no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-14_

Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário. Se um cliente já estiver instalado, o cliente abrirá e ingressará na reunião. Se um cliente não estiver instalado, por padrão, a versão 2013 do Lync Web App será aberta.

Você pode modificar o comportamento da página de associação de reunião se desejar permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant. Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet Set-CsWebServiceConfiguration.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Parâmetros do conjunto de páginas de associação de reunião-CsWebServiceConfiguration

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
<td><p>Se definido como true, os usuários que ingressam em uma reunião usando um aplicativo cliente que não seja o Lync terão a oportunidade de ingressar na reunião usando o Office Communicator 2007 R2. O valor padrão é False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Quando definida como true, as opções alternativas para ingressar em uma conferência online (como o Office Communicator 2007 R2) serão expandidas automaticamente e exibidas para os usuários. Quando definido como falso (o valor padrão), essas opções estarão disponíveis, mas o usuário precisará exibir a lista de opções para si mesmo.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Para configurar a página ingressar na reunião usando o Shell de gerenciamento do Lync Server 2013

1.  Inicie o Shell de gerenciamento do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Para exibir as configurações de serviço Web, execute o seguinte cmdlet:
    
        Get-CsWebServiceConfiguration

3.  Execute o comando a seguir, com os parâmetros definidos como verdadeiro ou falso, dependendo da sua preferência (para obter detalhes sobre os parâmetros para esse cmdlet, consulte [set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) na documentação do Shell de gerenciamento do Lync Server 2013):
    
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

