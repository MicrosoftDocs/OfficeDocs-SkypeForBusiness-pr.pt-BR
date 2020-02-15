---
title: 'Lync Server 2013: etapas para preparar e implantar o ambiente híbrido do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3326db7ce62279c4295bc13ec262a5a553ca5e62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Etapas para preparar e implantar o ambiente híbrido do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-12-08_

A tabela a seguir lista as etapas necessárias para preparar seu ambiente para uma implantação híbrida com o Skype for Business Online e o Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Concluído?</th>
<th>Etapa</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Criar uma conta de locatário para o Office 365 e habilitar o Lync Online</p></td>
<td><p>Saiba mais sobre o Office 365 e o Lync Online no <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</p>
<p>Para certificar-se de que seu ambiente está pronto para o Office 365, confira os <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">requisitos do sistema</a>.</p>
<p>Para obter detalhes sobre como configurar o Office 365, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with office 365</a> e <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Set up Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Adicionar seu domínio e verificar a propriedade</p></td>
<td><p>Seu domínio, às vezes, também é conhecido como seu <em>domínio personalizado</em>. Você deve adicionar seu domínio ao seu locatário do Office 365 e, em seguida, siga as etapas para validar o domínio com o Office 365. Isso é para confirmar que você é o proprietário do domínio.</p>
<p>Para adicionar seu domínio ao seu locatário do Office 365, siga as etapas descritas em <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Adicionar seu domínio ao Office 365</a>.</p>
<p>Conclua todas as etapas em cada seção do tópico, incluindo &quot;editar registros DNS para seus serviços do Office 365.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Verificar a preparação do ambiente</p></td>
<td><p>Você pode usar o assistente de configuração do Office 365 para ajudá-lo a implantar o Office 365. Para obter mais informações, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">usar o assistente de configuração para determinar a preparação do Office 365</a>.</p>
<p>Para obter detalhes sobre como usar a ferramenta e implantar o Office 365, confira o <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guia de implantação do office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Preparar a sincronização do Active Directory</p></td>
<td><p>A sincronização do Active Directory mantém o seu Active Directory no local sincronizado continuamente com o Office 365. Isso permite que você crie versões sincronizadas de cada conta de usuário e grupo, além de habilitar a sincronização de GAL (lista de endereços global) do ambiente local do Exchange Server para o Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> Você precisa sincronizar as contas do AD para todos os usuários do Lync em sua organização entre suas implantações locais e online do Lync, mesmo que os usuários não sejam movidos para o Lync Online. Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online em sua organização poderá não funcionar conforme o esperado.


</div>
<p>Para preparar seu ambiente para a sincronização do Active Directory, siga as etapas descritas no <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">mapa de sincronização de diretórios</a>, incluindo a configuração do logon único.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Criar certificados para serviços de Federação do Active Directory (AD FS)</p></td>
<td><p>Você precisará criar os certificados usados para a Federação de identidade com o Office 365. Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o logon único na <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">lista de verificação: Use o AD FS para implementar e gerenciar o logon único</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Atribuir certificados para AD FS</p></td>
<td><p>Depois de criar os certificados usados para a Federação de identidade com o Office 365, você deve instalá-los e atribuí-los.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Mover usuários piloto para o Skype for Business Online</p></td>
<td><p>Após concluir as etapas para preparar e configurar o seu ambiente para o Skype for Business Online, você pode começar a mover os usuários do piloto para o Lync Online.</p>
<p>Consulte <a href="lync-server-2013-move-users-to-lync-online.md">move users to Lync Online in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Administrar usuários em uma implantação híbrida</p></td>
<td><p>Para obter detalhes sobre como administrar usuários em uma implantação híbrida, consulte <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering Users in a Hybrid Lync Server 2013 Deployment</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

