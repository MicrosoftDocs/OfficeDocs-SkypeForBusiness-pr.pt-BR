---
title: 'Lync Server 2013: exportar um arquivo de configuração de rota de voz'
description: 'Lync Server 2013: exportar um arquivo de configuração de rota de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf342e11be41015df3cfd76f6a875381cb8b64
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564787"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>Exportar um arquivo de configuração de rota de voz no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Se você quiser salvar sua configuração de roteamento de voz sem publicá-la, siga estas etapas para usar os comandos exportar e importar da configuração do painel de controle do Lync Server para salvar e recuperar um instantâneo da sua configuração de roteamento de voz. Quando você importa um arquivo de configuração de roteamento de voz (. vcfg), mas foram feitas alterações na configuração de roteamento de voz no servidor enquanto isso, as páginas no grupo de **Roteamento de voz** no painel de controle do Lync Server indicarão que há alterações não confirmadas no roteamento de voz. Essas alterações não confirmadas são as diferenças entre as duas configurações que exigem reconciliação.

Se você tiver feito alterações não confirmadas nas configurações de qualquer página dentro do grupo, as alterações serão salvas no arquivo de configuração de voz exportado (. vcfg). Isso permite que você faça alterações de configuração de roteamento de voz durante várias sessões antes de publicar as alterações.

<div>

## <a name="to-export-a-voice-routing-configuration"></a>Para exportar uma configuração de roteamento de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de voz**.

4.  No menu **Ações**, clique em **Exportar configuração**.

5.  Especifique um local e nome de arquivo e então clique em **Salvar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Importar um arquivo de configuração de rota de voz no Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

