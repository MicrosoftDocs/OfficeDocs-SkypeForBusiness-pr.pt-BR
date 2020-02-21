---
title: Requisitos técnicos do Lync Server 2013 para conferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f28effa3ac80f4a2bca1fa062fcc3dfafb5d7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Requisitos técnicos para conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-25_

Para Lync Server 2013, conferência discada, conferência de A/V, recursos de conferência de mensagens instantâneas (IM) e webconferência sempre são executados em servidores front-end.

Esta seção detalha os requisitos de hardware e software para esses servidores, juntamente com a colocação de suporte.

A conferência discada é um recurso que contém vários componentes. Alguns destes componentes são específicos para conferência discada e alguns são componentes do Enterprise Voice. Esta seção descreve os requisitos para os componentes específicos para a conferência discada. Para obter detalhes sobre o servidor de mediação e os requisitos de gateway PSTN (rede telefônica pública comutada), consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) e [components for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

Como a conferência da Web e a conferência A/V são colocadas com o servidor front-end, os requisitos de hardware do servidor são os mesmos dos servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte. Os seguintes componentes necessários para a conferência discada também têm os mesmos requisitos de hardware que os servidores front-end:

  - Serviço de aplicativos

  - Aplicativo Atendedor de Conferência

  - Aplicativo Comunicado de Conferência

Os requisitos de hardware para o servidor front-end são os mesmos que para muitas outras funções de servidor no Lync Server 2013 são descritos na tabela a seguir.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

Como a conferência da Web e a conferência A/V são colocadas com o servidor front-end, os requisitos de software do servidor são os mesmos dos servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Para webconferência, o Lync Server 2013 também requer o Office Web Apps e o Office Web Apps Server (anteriormente conhecido como servidor WAC) para lidar com apresentações do PowerPoint. Para obter detalhes, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Para conferência discada, o serviço de aplicativo, o aplicativo de atendedor de conferência e o aplicativo de anúncio de conferência têm os mesmos requisitos do sistema operacional que os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Aplicativo de atendedor de conferência e anúncio de conferência o aplicativo exige que o Windows Media Format Runtime esteja instalado em servidores front-end. O Tempo de Execução do Windows Media Format é exigido para reproduzir arquivos WMA (áudio do Windows Media) que são usados parar músicas em espera, nomes registrados e avisos. Exceto para o Windows Server 2012 e o Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado automaticamente como parte da experiência da área de trabalho do Windows ao executar a instalação, mas talvez seja necessário reiniciar o computador. Portanto, é recomendável fazer a instalação como parte da Experiência de Desktop do Windows, que inclui o Tempo de Execução do Windows Media Format, antes de executar a Instalação. O Windows Server 2012 e o Windows Server 2012 R2 exigem o Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Requisitos de porta para a conferência discada

A tabela a seguir descreve as portas que são usadas pela conferência discada. Se estiver usando um balanceador de carga, verifique se ele está configurado para as portas usadas por todos os aplicativos que serão executados no pool.

Essas portas são as configurações padrão que podem ser alteradas com o uso do cmdlet **Set-CsApplicationServer**. Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.

<div>


> [!NOTE]  
> Todas as instâncias do mesmo aplicativo em um pool usam a mesma porta de escuta SIP.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Portas usadas pelas conferência discada

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número da porta</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>Usado pelo aplicativo de atendedor de conferência para solicitações de escuta SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Usado pelo aplicativo comunicado de conferência para solicitações de escuta SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Clientes suportados para conferência discada

É possível usar o seguinte cliente para agendar conferências locais que dão suporte ao acesso discado:

  - Suplemento de reunião online para Lync 2013 (instalado automaticamente quando você instala o Lync 2013 ou participante)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Requisitos da página de configurações de conferência discada

A página de configurações de conferência discada suporta as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.

<div>


> [!NOTE]  
> Versões de 32 bits e 64 bits dos sistemas operacionais são suportadas.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Sistemas operacionais e navegadores da Web suportados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operacional</th>
<th>Navegador da Web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de arquivo de áudio para conferência discada

O Lync Server 2013 não é compatível com a personalização de prompts de voz e música para conferência discada. No entanto, se você tiver uma forte necessidade de negócios que exija a alteração dos arquivos de áudio padrão, consulte o artigo 961177 da base de dados de conhecimento da Microsoft, [como personalizar prompts de voz ou arquivos de música para conferência de áudio de discagem no Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Você também pode usar o utilitário de gerenciamento de [voz personalizado do atendedor de conferência do Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkid=396880) , que permite aos administradores substituir os prompts de voz padrão usados quando um chamador de telefone ingressar em uma reunião do Lync com prompts personalizados para fornecer uma experiência de entrada de reunião diferente. Os prompts de voz personalizados podem ser instalados em um servidor que esteja executando o Lync Server 2010 ou o Lync Server 2013, Enterprise ou Standard Edition.

O aplicativo atendedor de conferência e anúncio de conferência têm os seguintes requisitos para arquivos de música em espera, nomes gravados e prompts de áudio:

  - Formato de arquivo WMA (áudio do Windows Media)

  - 16 bits mono

  - 48 kbps 2-pass CBR (taxa de bits constante)

  - Nível da fala a -24 DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos do usuário para conferência discada

Os usuários de conferências discadas devem ter um número de telefone ou extensão exclusivos atribuídos à respectiva conta. Este requisito oferece suporte à autenticação durante a conferência discada. Usuários corporativos (ou seja, usuários que têm credenciais de serviços de domínio do Active Directory e contas do Lync Server em sua organização) inserem seus números de telefone (ou ramal) e um número de identificação pessoal (PIN) para discar para conferências como um usuário autenticado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

