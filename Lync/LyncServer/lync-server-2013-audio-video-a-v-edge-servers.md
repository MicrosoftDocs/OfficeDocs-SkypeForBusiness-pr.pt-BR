---
title: 'Lync Server 2013: servidores de borda de áudio/vídeo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O serviço de borda A/V fornece uma maneira para seus usuários internos (usuários que estão conectados à sua rede organizacional) para compartilhar áudio e vídeo com usuários externos (usuários que não estão conectados à sua rede organizacional). Além de áudio e vídeo, o serviço de borda A/V também oferece suporte para tarefas de compartilhamento de área de trabalho e transferência de arquivos.

O serviço de borda A/V é gerenciado principalmente usando-se A configuração de borda A/V; essas configurações permitem que você gerencie a quantidade máxima de largura de banda a ser alocada por porta e por usuário e especifique o período de tempo que um token de autenticação pode ser usado antes de o token ser renovado. As configurações de borda a/V podem ser aplicadas a sites ou a servidores de borda A/V individuais. Ao determinar quais conjuntos de configurações terão prioridade, use o seguinte guia:

  - As configurações definidas no escopo do serviço (ou seja, em um servidor individual) têm prioridade sobre tudo.

  - As configurações definidas no escopo do site têm prioridade sobre as configurações definidas no escopo global. No entanto, as configurações de escopo do serviço também substituirão as configurações de escopo do site.

  - As configurações no escopo global serão usadas apenas se não houver configurações de serviço configuradas no servidor individual e se não houver configurações de site para o site em que o servidor está localizado.

O serviço de borda A/V só pode ser gerenciado usando o Lync Server PowerShell e os cmdlets CsAVEdgeConfiguration.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Criar ou modificar um conjunto de configurações de servidor de borda A/V no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Excluir uma coleção existente de configurações de servidor de borda A/V no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

