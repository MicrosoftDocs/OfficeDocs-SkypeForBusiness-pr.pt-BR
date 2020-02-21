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
ms.openlocfilehash: 7dde4cfdc2f027c095cd6ad95582a130d047d3c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>Importar políticas e configurações

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Após mesclar as informações de topologia do Office Communications Server 2007 R2 com o pool piloto do Lync Server 2013, você precisará executar um cmdlet do Shell de gerenciamento do Lync Server 2013 para migrar suas políticas e configurações do Office Communications Server 2007 R2 para o pool piloto do Lync Server 2013.

O cmdlet **Import-CsLegacyConfiguration** importa políticas, rotas de voz, planos de discagem, URLs do Communicator Web Access e números de acesso discado para o Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Para migrar as configurações e políticas

1.  No servidor front-end do Lync Server 2013, inicie o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
        Import-CsLegacyConfiguration
    
    Após a importação das políticas, use o procedimento a seguir para ver as políticas importadas no painel de controle do Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Para ver as políticas importadas

1.  Abra o painel de controle do Lync Server 2013.

2.  Clique em **Roteamento de Voz** e veja as políticas importadas.

3.  Clique em **Conferência** e veja as políticas importadas.

4.  Click **Federation and External Access** and view the imported policies.

5.  Clique em **Monitoramento e Arquivamento** e veja as políticas importadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

