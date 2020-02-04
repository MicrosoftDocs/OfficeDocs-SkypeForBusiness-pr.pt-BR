---
title: Importar políticas e configurações
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>Importar políticas e configurações

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Depois de mesclar as informações de topologia do Office Communications Server 2007 R2 com o pool piloto do Lync Server 2013, você precisa executar um cmdlet do Shell de gerenciamento do Lync Server 2013 para migrar suas configurações e políticas do Office Communications Server 2007 R2 para o pool piloto do Lync Server 2013.

O cmdlet **Import-CsLegacyConfiguration** importa políticas, rotas de voz, planos de discagem, URLs do Communicator Web Access e números de acesso discada para o Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Para migrar políticas e configurações

1.  No servidor de front-end do Lync Server 2013, inicie o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
        Import-CsLegacyConfiguration
    
    Depois que as políticas forem importadas, use o procedimento a seguir para ver as políticas importadas no painel de controle do Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Para exibir as políticas importadas

1.  Abra o painel de controle do Lync Server 2013.

2.  Clique em **Roteamento de voz** e veja as políticas importadas.

3.  Clique em **conferência** e veja as políticas importadas.

4.  Clique em **Federação e acesso externo** e veja as políticas importadas.

5.  Clique em **monitoramento e arquivamento** e veja as políticas importadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

