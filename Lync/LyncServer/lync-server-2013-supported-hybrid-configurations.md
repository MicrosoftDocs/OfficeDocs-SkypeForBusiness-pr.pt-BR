---
title: 'Lync Server 2013: configurações híbridas com suporte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34a73d343375f53acf7f1b7383efb05dd63b9a64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configurações híbridas do Lync Server 2013 com suporte

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-05-10_

Você pode configurar as implantações do Lync Server 2013 para integração com o Microsoft Exchange Server 2010 e com o Microsoft Exchange Server 2013 e o SharePoint Server, tanto no local quanto online. Os recursos listados na tabela a seguir são compatíveis com todos os clientes, a menos que especificado de outra forma. Para obter mais informações sobre o suporte ao cliente, consulte [Client Comparison Tables for Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) and Skype for Business online comparation Tables at clients [for Skype for Business online](https://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integração com o Exchange Server

A tabela a seguir lista os recursos suportados em uma implantação híbrida quando integrado com o Microsoft Exchange Server.


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
<p>Para obter mais informações, consulte <a href="lync-server-2013-im-and-presence.md">im e presença no Lync Server 2013</a></p></li>
<li><p>Agendar e ingressar em reuniões online por meio do Outlook</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">integrando o Microsoft Lync server 2013 e o Microsoft Exchange server 2013</a></p></li>
<li><p>IM/presença no Outlook Web App</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Configuring Microsoft Lync Server 2013 in a Cross-premises Environment</a></p></li>
<li><p>Agendar e ingressar em reuniões online por meio do Outlook Web App</p></li>
<li><p>IM/presença em clientes móveis</p></li>
<li><p>Ingressar em reuniões online em clientes móveis</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-deploying-mobility.md">Deploying Mobility in Lync Server 2013</a></p></li>
<li><p>Publicar status com base nas informações de disponibilidade do calendário do Outlook</p></li>
<li><p>Lista de contatos (via repositório unificado de contatos)</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the Unified Contact Store</a></p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.<BR>Um cliente do Lync 2013 desktop é necessário.


</div></li>
<li><p>Foto de contato de alta resolução no Lync 2013 Client e no Lync Web App.</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configurando o uso de fotos de alta resolução no Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.


</div></li>
<li><p>Delegação de reunião</p>
<p>Suportado somente quando os dois usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
<li><p>O histórico de conversas perdidas e os logs de chamadas são gravados na caixa de correio do Exchange do usuário</p></li>
<li><p>Arquivamento de conteúdo (IM e reunião) no Exchange</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment Checklist for Archiving in Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.


</div></li>
<li><p>Pesquisar conteúdo arquivado</p>
<div>

> [!NOTE]  
> Requer o Exchange 2013.


</div></li>
<li><p>Caixa postal</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Deploying on-premises Exchange um to fornecer Lync Server 2013 voice mail</a></p></li>
</ul></td>
<td><ul>
<li><p>IM/presença no Outlook</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Agendar e ingressar na reunião online por meio do Outlook</p></li>
<li><p>IM/presença no OWA</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>Agendar e ingressar na reunião online no Outlook Web App</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a></p></li>
<li><p>IM/presença em clientes móveis</p></li>
<li><p>Ingressar na reunião online em clientes móveis</p></li>
<li><p>Publicar status com base nas informações de disponibilidade do calendário do Outlook</p></li>
<li><p>Lista de contatos (via repositório unificado de contatos). Para obter mais informações, consulte <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuring Microsoft Lync Server 2013 to use the Unified Contact Store</a></p>
<div>

> [!NOTE]  
> Lync Server 2013 apenas. Um cliente do Lync 2013 desktop é necessário.


</div></li>
<li><p>Foto de contato de alta resolução no Lync 2013 Client e no Lync Web App.</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuring the Use of High-Resolution Photos in Microsoft Lync Server 2013</a>.</p></li>
<li><p>Delegação de reunião</p>
<p>Suportado somente quando os dois usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
<li><p>O histórico de conversas perdidas e os logs de chamadas são gravados na caixa de correio do Exchange do usuário</p></li>
<li><p>Arquivamento de conteúdo (IM e reunião) no Exchange.</p>
<p>Para obter mais informações, consulte <a href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment Checklist for Archiving in Lync Server 2013</a></p></li>
<li><p>Pesquise o conteúdo arquivado. Confira mais informações em <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configurar o Exchange para o centro de descoberta eletrônica do SharePoint</a></p></li>
<li><p>Caixa postal. Para obter mais informações, consulte <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">fornecer Lync Server 2013 Users voice mail on Hosted Exchange um</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>IM e presença no Outlook</p></li>
<li><p>Agendar e ingressar em reuniões online por meio do Outlook</p></li>
<li><p>IM/presença em clientes móveis</p></li>
<li><p>O histórico de conversas perdidas e os logs de chamadas são gravados na caixa de correio do Exchange do usuário</p></li>
<li><p>Foto de contato de alta resolução no cliente do Lync 2013.</p>
<div>

> [!NOTE]  
> Requer o Microsoft Exchange Server 2013. Isso não é suportado no Lync Web App quando os usuários são hospedados no Skype for Business online.


</div></li>
<li><p>Ingressar na reunião online em clientes móveis</p></li>
<li><p>Publicar status com base nas informações de disponibilidade do calendário do Outlook</p></li>
<li><p>Delegação de reunião</p>
<p>Suportado somente quando os dois usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
</ul></td>
<td><ul>
<li><p>IM/presença no Outlook</p></li>
<li><p>Agendar e ingressar em reuniões online por meio do Outlook</p></li>
<li><p>IM/presença no Outlook Web App</p></li>
<li><p>Agendar e ingressar na reunião online no Outlook Web App</p></li>
<li><p>IM/presença em clientes móveis</p></li>
<li><p>Ingressar na reunião online em clientes móveis</p></li>
<li><p>Publicar status com base nas informações de disponibilidade do calendário do Outlook</p></li>
<li><p>O histórico de conversas perdidas e os logs de chamadas são gravados na caixa de correio do Exchange do usuário</p></li>
<li><p>Lista de contatos (via repositório unificado de contatos)</p>
<div>

> [!NOTE]  
> Cliente do Lync Server 2013 necessário


</div></li>
<li><p>Foto de contato de alta resolução no cliente Lync 2013 e Lync Web App</p></li>
<li><p>Delegação de reunião</p>
<p>Suportado somente quando os dois usuários estão hospedados online na mesma floresta ou quando ambos estão hospedados no local.</p></li>
<li><p>Arquivamento de conteúdo (IM e reunião) no Exchange</p></li>
<li><p>Pesquisar conteúdo arquivado</p></li>
<li><p>Caixa postal</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integração com o SharePoint

A tabela a seguir lista os recursos suportados em uma implantação híbrida do Lync Server 2013 quando integrado com o SharePoint.


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

