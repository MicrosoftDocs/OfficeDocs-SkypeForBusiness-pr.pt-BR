---
title: Lista de verificação de implantação do Lync Server 2013 para conferência A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 736719475d77f67932b350e1684b4af26ca2fbd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Lista de verificação de implantação para conferência A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Assim como com a implantação de outros componentes do Lync Server 2013, A implantação de uma conferência A/V requer que você use o construtor de topologias para criar e publicar uma topologia que incorpora conferências.

<div>

## <a name="deployment-sequence"></a>Sequência de implantação

Você pode implantar conferências ao mesmo tempo em que implantar a sua topologia inicial ou depois de implantar pelo menos um pool de front-end ou um servidor Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Processo de implantação de conferência

A tabela a seguir fornece uma visão geral das etapas necessárias para implantar a conferência em uma topologia existente.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Funções e associações de grupo</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar pré-requisitos de hardware e software</strong></p></td>
<td><p>A conferência é executada em servidores front-end de um pool de front-end e servidores Standard Edition. Não há requisitos adicionais de hardware ou software além daqueles necessários para instalar esses servidores.</p>
<div>

> [!NOTE]  
> O Lync Server 2013 usa o Office Web Apps e o Office Web Apps Server para lidar com o compartilhamento e a renderização de apresentações do PowerPoint. Para obter detalhes sobre como instalar e configurar o Office Web Apps Server, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o Office Web Apps Server e o Lync Server 2013</A>.


</div></td>
<td><p>Domínio do usuário que é membro do grupo local de Administradores</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware com suporte para o Lync Server 2013</a> na documentação de suporte</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte de software e infraestrutura do servidor no Lync Server 2013</a> na documentação de suporte</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinação dos requisitos do sistema para o Lync Server 2013</a> na documentação de planejamento.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crie a topologia interna apropriada para dar suporte à conferência</strong></p></td>
<td><p>Execute o construtor de topologias para adicionar conferências à topologia e, em seguida, publique a topologia.</p></td>
<td><p>Para definir a topologia, uma conta que é membro do grupo local de Usuários</p>
<p>Para publicar a topologia, uma conta que é membro do grupo Domain admins e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivos a ser usado para o repositório de arquivos do Lync Server 2013 (para que o construtor de topologias possa configurar as DACLs necessárias)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Defina e configure uma topologia no construtor de topologias para o Lync Server 2013</a> na documentação de implantação.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar políticas de conferência e suporte</strong></p></td>
<td><p>Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de conferência.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribuir usuários à função [] ou CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Políticas de conferência no Lync Server 2013</a> na documentação de operações.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral de conferência no Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Definindo seus requisitos para conferência no Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

