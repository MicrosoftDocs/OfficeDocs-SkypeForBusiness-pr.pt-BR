---
title: 'Lync Server 2013: configurações híbridas com suporte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142b86720e64fdfd071bc5cacb21e4891e3e7758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configurações híbridas do Lync Server 2013 com suporte

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-05-10_

Você pode configurar as implantações do Lync Server 2013 para integração com o Microsoft Exchange Server 2010 e o Microsoft Exchange Server 2013 e o SharePoint Server, tanto local quanto online. Os recursos listados na tabela a seguir têm suporte em todos os clientes, a menos que haja uma especificação diferente. Para obter mais informações sobre o suporte ao cliente, consulte [tabelas de comparação de clientes para as tabelas de comparação de clientes do Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) e do Skype for Business online em [clientes para o Skype for Business online](http://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integração com o Exchange Server

A tabela a seguir lista os recursos com suporte em uma implantação híbrida quando integrado ao Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange local</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 local</strong></p></td>
<td><ul>
<li><p>IM/presença no Outlook</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-im-and-presence.md">mensagens instantâneas e presença no Lync Server 2013</a></p></li>
<li><p>Agende e participe de reuniões online via Outlook</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a></p></li>
<li><p>Mensagem instantânea/presença no Outlook Web App</p>
<p>Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">o Microsoft Lync Server 2013 em um ambiente de várias instalações</a></p></li>
<li><p>Agende e participe de reuniões online via Outlook Web App</p></li>
<li><p>IM/Presença em clientes de dispositivos móveis</p></li>
<li><p>Participe de reuniões online em clientes de dispositivos móveis</p>
<p>Para obter mais informações, consulte Implantando o <a href="lync-server-2013-deploying-mobility.md">Mobility no Lync Server 2013</a></p></li>
<li><p>Publique o status com base nas informações de ocupado/livre do calendário do Outlook</p></li>
<li><p>Lista de contatos (via repositório de contato unificado)</p>
<p>Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">o Microsoft Lync Server 2013 para usar o repositório de contatos</a> unificado</p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.<BR>É necessário um cliente de desktop Lync 2013.


</div></li>
<li><p>Foto de contato de alta resolução no Lync 2013 cliente e no Lync Web App.</p>
<p>Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">o uso de fotos de alta resolução no Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.


</div></li>
<li><p>Delegação da reunião</p>
<p>Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
<li><p>O histórico de Conversas Perdidas e Registros de Chamadas são escritos para a caixa de correio do Exchange do usuário</p></li>
<li><p>Arquivamento de conteúdo (IM e reunião) no Exchange</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-deployment-checklist-for-archiving.md">lista de verificação de implantação para arquivamento no Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.


</div></li>
<li><p>Pesquise o conteúdo arquivado</p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.


</div></li>
<li><p>Caixa postal</p>
<p>Para obter mais informações, consulte Implantando o <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Exchange um local para fornecer correio de voz do Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>IM/presença no Outlook</p>
<p>Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">a integração do Lync Server 2013 local com o Exchange Online</a></p></li>
<li><p>Agende e participe de reuniões online via Outlook</p></li>
<li><p>IM/Presença em OWA</p>
<p>Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">a integração do Lync Server 2013 local com o Exchange Online</a></p></li>
<li><p>Agendar e ingressar em reunião online a partir do Outlook Web App</p>
<p>Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">a integração do Lync Server 2013 local com o Exchange Online</a></p></li>
<li><p>IM/Presença em clientes de dispositivos móveis</p></li>
<li><p>Participe de uma reunião online em clientes de dispositivos móveis</p></li>
<li><p>Publique o status com base nas informações de ocupado/livre do calendário do Outlook</p></li>
<li><p>Lista de contatos (via repositório de contato unificado). Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">o Microsoft Lync Server 2013 para usar o repositório de contatos</a> unificado</p>
<div>

> [!NOTE]  
> Somente Lync Server 2013. É necessário um cliente de desktop Lync 2013.


</div></li>
<li><p>Foto de contato de alta resolução no Lync 2013 cliente e no Lync Web App.</p>
<p>Para obter mais informações, consulte Configurando <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">o uso de fotos de alta resolução no Microsoft Lync Server 2013</a>.</p></li>
<li><p>Delegação da reunião</p>
<p>Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
<li><p>O histórico de Conversas Perdidas e Registros de Chamadas são escritos para a caixa de correio do Exchange do usuário</p></li>
<li><p>Arquivamento de conteúdo (IM e reunião) no Exchange.</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-deployment-checklist-for-archiving.md">lista de verificação de implantação para arquivamento no Lync Server 2013</a></p></li>
<li><p>Pesquise o conteúdo arquivado. Para obter mais informações, consulte em <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Configurar o centro de descoberta automática do Exchange para SharePoint</a></p></li>
<li><p>Caixa postal. Para obter mais informações, consulte <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">fornecendo aos usuários do Lync Server 2013 o correio de voz no Hosted Exchange um</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Mensagens instantâneas e presença no Outlook</p></li>
<li><p>Agende e participe de reuniões online via Outlook</p></li>
<li><p>IM/Presença em clientes de dispositivos móveis</p></li>
<li><p>O histórico de Conversas Perdidas e Registros de Chamadas são escritos para a caixa de correio do Exchange do usuário</p></li>
<li><p>Foto de contato de alta resolução no cliente do Lync 2013.</p>
<div>

> [!NOTE]  
> Requer o Microsoft Exchange Server 2013. Isso não é compatível com o Lync Web App quando os usuários são hospedados no Skype for Business online.


</div></li>
<li><p>Participe de uma reunião online em clientes de dispositivos móveis</p></li>
<li><p>Publique o status com base nas informações de ocupado/livre do calendário do Outlook</p></li>
<li><p>Delegação da reunião</p>
<p>Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
</ul></td>
<td><ul>
<li><p>IM/presença no Outlook</p></li>
<li><p>Agende e participe de reuniões online via Outlook</p></li>
<li><p>Mensagem instantânea/presença no Outlook Web App</p></li>
<li><p>Agendar e ingressar em reunião online a partir do Outlook Web App</p></li>
<li><p>IM/Presença em clientes de dispositivos móveis</p></li>
<li><p>Participe de uma reunião online em clientes de dispositivos móveis</p></li>
<li><p>Publique o status com base nas informações de ocupado/livre do calendário do Outlook</p></li>
<li><p>O histórico de Conversas Perdidas e Registros de Chamadas são escritos para a caixa de correio do Exchange do usuário</p></li>
<li><p>Lista de contatos (via repositório de contato unificado)</p>
<div>

> [!NOTE]  
> Cliente do Lync Server 2013 necessário


</div></li>
<li><p>Foto de contato de alta resolução no cliente do Lync 2013 e no Lync Web App</p></li>
<li><p>Delegação da reunião</p>
<p>Com suporte apenas quando ambos os usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
<li><p>Arquivamento de conteúdo (IM e reunião) no Exchange</p></li>
<li><p>Pesquise o conteúdo arquivado</p></li>
<li><p>Caixa postal</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integração com SharePoint

A tabela a seguir lista os recursos com suporte em uma implantação híbrida do Lync Server 2013 quando integrado com o SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint local</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 local</strong></p></td>
<td><ul>
<li><p>Pesquisa de habilidades</p></li>
<li><p>Presença no SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Presença no SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Presença no SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Presença no SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

