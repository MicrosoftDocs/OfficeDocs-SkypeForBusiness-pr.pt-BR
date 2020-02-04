---
title: 'Lync Server 2013: Requisitos técnicos para conferência'
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
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Requisitos técnicos para conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-25_

Para o Lync Server 2013, conferência discada, conferência A/V, conferências de mensagens instantâneas e recursos de Webconferência sempre são executados em servidores front-end.

Esta seção detalha os requisitos de hardware e software para esses servidores, além da colocação de suporte.

A conferência discada é um recurso que inclui diversos componentes. Alguns dos componentes são específicos para conferência discada e alguns são componentes do Enterprise Voice. Esta seção descreve os requisitos para os componentes específicos da conferência discada. Para obter detalhes sobre o servidor de mediação e requisitos de gateway PSTN (rede telefônica pública comutada), consulte [componente servidor de mediação no Lync server 2013](lync-server-2013-mediation-server-component.md) e [componentes e topologias do servidor de mediação no Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.

<div>

## <a name="hardware-requirements"></a>Requisitos de hardware

Como a conferência da Web e conferência A/V são posicionadas com o servidor front-end, os requisitos de hardware do servidor são os mesmos para os servidores front-end. Para obter detalhes sobre os requisitos de hardware, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte. Os seguintes componentes necessários para a conferência discada também têm os mesmos requisitos de hardware que os servidores front-end:

  - Serviço de aplicativos

  - Aplicativo Atendedor de Conferência

  - Aplicativo Comunicado de Conferência

Os requisitos de hardware para front-end Server são os mesmos para muitas outras funções de servidor no Lync Server 2013 são descritas na tabela a seguir.

</div>

<div>

## <a name="software-requirements"></a>Requisitos de software

Como a conferência da Web e conferência A/V estão posicionadas com o servidor front-end, os requisitos de software do servidor são os mesmos para os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Para webconferência, o Lync Server 2013 também requer o Office Web Apps e o Office Web Apps Server (anteriormente conhecido como WAC Server) para manipular apresentações do PowerPoint. Para obter detalhes, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Para conferência discada, serviço de aplicativo, aplicativo atendedor de conferência e aplicativo de anúncio de conferência têm os mesmos requisitos de sistema operacional que os servidores front-end. Para obter detalhes sobre os requisitos de software, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.

Aplicativo de atendedor de conferência o aplicativo de anúncio de conferência requer que o tempo de execução do Windows Media Format seja instalado em servidores front-end. O tempo de execução do Windows Media Format é necessário para reproduzir arquivos de áudio do Windows Media (WMA) usados para música em espera, nomes gravados e solicitações. Com exceção do Windows Server 2012 e do Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado automaticamente como parte da experiência da área de trabalho do Windows quando você executa a instalação, mas talvez seja necessário reiniciar o computador. Portanto, recomendamos que você instale como parte da experiência da área de trabalho do Windows, que inclui o tempo de execução do Windows Media Format antes de executar a instalação. O Windows Server 2012 e o Windows Server 2012 R2 exigem o Microsoft Media Foundation.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Requisitos de porta para conferência discada

A tabela a seguir descreve as portas usadas pela conferência discada. Se você usar um balanceador de carga, certifique-se de que o balanceador de carga está configurado para as portas usadas por quaisquer aplicativos que serão executados no pool.

Essas portas são configurações padrão que podem ser alteradas usando o cmdlet **set-CsApplicationServer** . Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.

<div>


> [!NOTE]  
> Todas as instâncias do mesmo aplicativo em um pool usam a mesma porta de escuta SIP.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Portas usadas pela conferência discada

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
<td><p>Usado pelo aplicativo de assistente de conferência para solicitações de escuta SIP</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Usado pelo aplicativo de anúncio de conferência para solicitações de escuta SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Clientes com suporte para conferência discada

Você pode usar o seguinte cliente para programar conferências locais que dão suporte ao acesso de discagem:

  - Suplemento de reunião online do Lync 2013 (instalado automaticamente quando você instala o Lync 2013 ou participante)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Requisitos da página de configurações de conferência discada

A página Configurações de conferência discada aceita as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.

<div>


> [!NOTE]  
> Há suporte para as versões de 32 bits e 64 bits dos sistemas operacionais.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Navegadores da Web e sistemas operacionais com suporte

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

O Lync Server 2013 não é compatível com a personalização de prompts de voz e música para conferência discada. No entanto, se você tiver uma forte necessidade empresarial que exija a alteração dos arquivos de áudio padrão, consulte o artigo 961177 da base de dados de conhecimento Microsoft, [como personalizar prompts de voz ou arquivos de música para conferências de áudio discadas no Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Você também pode usar o utilitário de gerenciamento de [solicitações de voz personalizado do atendedor do Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880) , que permite aos administradores substituir as solicitações de voz padrão usadas quando um chamador de telefone ingressar em uma reunião do Lync com avisos personalizados para fornecer uma experiência de entrada de reunião diferente. Os prompts de voz personalizados podem ser instalados em um servidor que esteja executando o Lync Server 2010 ou o Lync Server 2013, Enterprise ou Standard Edition.

Aplicativo de atendedor de conferência o aplicativo de anúncio de conferência tem os seguintes requisitos para músicas em espera, nomes gravados e arquivos de prompt de áudio:

  - Formato de arquivo WMA (áudio do Windows Media)

  - 16 bits mono

  - 48 kbps 2-pass CBR (taxa de bits constante)

  - Nível da fala a -24 DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos do usuário para conferência discada

Os usuários de conferências discadas devem ter um número de telefone ou extensão exclusivos atribuídos à respectiva conta. Este requisito oferece suporte à autenticação durante a conferência discada. Usuários corporativos (ou seja, os usuários que têm credenciais de serviços de domínio Active Directory e contas do Lync Server em sua organização) inserem o número de telefone (ou ramal) e um número de identificação pessoal (PIN) para discar para conferências como um usuário autenticado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

