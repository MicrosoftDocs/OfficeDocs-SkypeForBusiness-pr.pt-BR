---
title: Lync Server 2013 lista de verificação de implantação para Webconferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86390987613c06bbd422edbea3432999751263c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Lista de verificação de implantação para Webconferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-30_

Assim como a implantação de outros componentes do Lync Server 2013, a implantação de Webconferência requer que você use o construtor de topologias para criar e publicar uma topologia que incorpore a conferência.

<div>

## <a name="deployment-sequence"></a>Sequência de implantação

Você pode implantar a conferência ao mesmo tempo em que implanta a topologia inicial ou após implantar pelo menos um pool de front-ends ou servidor Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Processo de implantação de conferências

A tabela a seguir fornece uma visão geral das etapas necessárias para implantar conferências em uma topologia existente.


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
<th>Associações a grupos e funções</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar pré-requisitos de hardware e software</strong></p></td>
<td><p>A conferência é executada em servidores front-end em um pool de front-ends e servidores Standard Edition. Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.</p>
<div>

> [!NOTE]  
> O Lync Server 2013 usa o Office Web Apps e o servidor do Office Web Apps para lidar com o compartilhamento e a renderização de apresentações do PowerPoint. Para obter informações sobre como instalar e configurar o servidor do Office Web Apps, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.


</div></td>
<td><p>Usuário do domínio que é membro do grupo local de Administradores</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> na documentação de suporte</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> na documentação de suporte</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinando os requisitos do sistema para o Lync Server 2013</a> na documentação de planejamento.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crie a topologia interna apropriada para dar suporte a conferências</strong></p></td>
<td><p>Execute o construtor de topologias para adicionar a conferência à topologia e, em seguida, publique a topologia.</p></td>
<td><p>Para definir a topologia, uma conta que é membro do grupo local de Usuários</p>
<p>Para publicar a topologia, uma conta que é membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivo a ser usado para o repositório de arquivos do Lync Server 2013 (de modo que o construtor de topologias possa configurar as DACLs necessárias)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definir e configurar uma topologia no construtor de topologias para o Lync Server 2013</a> na documentação de implantação.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar políticas e suporte de conferências</strong></p></td>
<td><p>Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de conferência.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribuir usuários à função [] ou CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Políticas de conferência no Lync Server 2013</a> na documentação de operações.</p></td>
</tr>
</tbody>
</table>


O Lync Server 2013 agora inclui a configuração **MaxUploadFileSizeMb** , que limita o tamanho dos arquivos que podem ser carregados durante uma reunião. O valor padrão para essa configuração é 500 MB. Você pode ajustar **MaxUploadFileSizeMb** usando o cmdlet **set-CsConferencingConfiguration** .

**MaxUploadFileSizeMb** não limita a configuração de carregamento de arquivo para o Lync Web App. O limite de carregamento de tamanho de arquivo para Lync Web App é definido como aproximadamente 30MB e é controlado pelo arquivo Web. config do\[IIS\]:/DataCollabWeb/int ext/Handler/Web.config. Para configurar o limite de carregamento de tamanho de arquivo do Lync Web `maxRequestLength` app `maxAllowedContentLength` , atualize e no arquivo Web. config, conforme mostrado abaixo.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Você deve atualizar o arquivo Web. config para cada servidor de front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

