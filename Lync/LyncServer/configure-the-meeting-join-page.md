---
title: Configurar a página de ingresso na reunião
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10700dc8a75d5c067870b53c0e0e74b7a469504a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>Configurar a página de ingresso na reunião

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-14_

Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de ingresso na reunião detecta se um cliente do Lync 2013 já está instalado no computador do usuário. Se um cliente já estiver instalado, esse cliente abre e participa da reunião. Se um cliente não estiver instalado, por padrão, a versão 2013 do Lync Web App é aberta.

Você pode modificar o comportamento da página de ingresso na reunião se quiser permitir que os usuários ingressem em reuniões com o Office Communicator 2007 R2 ou o Lync 2010 Attendant. Essas opções de configuração foram removidas do painel de controle do Lync Server 2013, mas você as configura usando o cmdlet CsWebServiceConfiguration.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>Parâmetros CsWebServiceConfiguration da página de ingresso em reunião

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parâmetro CsWebServiceConfiguration</th>
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

2.  Execute o seguinte cmdlet:
    
        Get-CsWebServiceConfiguration
    
    Este cmdlet retorna as definições de configurações do serviço da Web.

3.  Execute o seguinte comando, com os parâmetros definidos como true ou false, dependendo da sua preferência (para obter detalhes sobre os parâmetros desse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server 2013):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

