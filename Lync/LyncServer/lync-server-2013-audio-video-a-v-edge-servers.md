---
title: 'Lync Server 2013: servidores de borda de áudio/vídeo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62f31721b21e8738dcd57dfb203d7fd306c38c94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O Serviço de borda A/V fornece uma maneira para que seus usuários internos (usuários conectados à sua rede organizacional) compartilhem áudio e vídeo com usuários externos (usuários que não estão conectados à rede organizacional). Além de áudio e vídeo, o serviço de borda A/V fornece suporte para o compartilhamento de área de trabalho e a transferência de arquivos.

O serviço de borda A/V é gerenciado principalmente usando a configuração de borda A/V; essas configurações permitem que você gerencie a quantidade máxima de largura de banda que será alocada por porta e usuário, bem como para especificar por quanto tempo um token de autenticação pode ser usado antes de precisar renová-lo. As definições de configuração de borda A/V podem ser aplicadas a sites ou servidores de borda A/V individuais. Ao determinar qual conjunto de configurações terá prioridade, use o seguinte guia:

  - As definições configuradas no escopo de serviço (isto é, em um servidor individual ) têm prioridade sobre tudo.

  - As definições configuradas no escopo do site têm prioridade sobre as definições configuradas no escopo global. No entanto, as definições de escopo de serviço também substituem as configurações de escopo do site.

  - As configurações no escopo global serão usadas somente se não há definições de serviço configuradas no servidor individual e se não há configurações de site para o site onde o servidor está localizado.

O serviço de borda A/V só pode ser gerenciado com o uso do Lync Server PowerShell e dos cmdlets CsAVEdgeConfiguration.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

