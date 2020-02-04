---
title: 'Lync Server 2013: Preparando a floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a485ba2a406fd762d70ba4e8ff621d2d6af3801
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Preparando a floresta para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

A preparação da floresta cria configurações e objetos globais do Active Directory e grupos universais do Active Directory para uso pelo Lync Server 2013 e concede permissões de acesso adequadas nos objetos do Active Directory. Para obter uma descrição dos grupos universais e das configurações globais e dos objetos criados pela preparação da floresta, consulte [as alterações feitas pela preparação da floresta no Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

A preparação da floresta também cria objetos que contêm conjuntos de propriedades e especificadores de exibição que são usados pelo Lync Server 2013 e os armazena no contêiner de configuração.

<div>


> [!IMPORTANT]  
> Verifique se as alterações de preparação do esquema foram duplicadas para todos os controladores de domínio antes de executar o procedimento de preparação da floresta. Se a duplicação não for completada, ocorrerá um erro.



</div>

Se você estiver executando uma nova implantação do Lync Server, deverá armazenar as configurações globais no contêiner de configuração. Se você estiver atualizando de uma versão anterior e ainda armazenar configurações globais no contêiner do sistema, poderá continuar a usar o contêiner do sistema.

Você deve ser membro do grupo Administradores da empresa ou administradores de domínio do domínio raiz da floresta para executar esse procedimento.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Executando preparação de floresta para Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Usando cmdlets para reverter preparação da floresta no Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

