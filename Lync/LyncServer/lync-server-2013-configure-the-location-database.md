---
title: 'Lync Server 2013: configurar o banco de dados de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15a9456cc79e02735fe94c24748674944722b49c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configure the location database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-17_

Para que os clientes possam detectar automaticamente seu local na rede, primeiro configure o banco de dados de localização. Se você não configurar um banco de dados de local e a **localização necessária** na política de localização estiver definida como **Sim** ou isenção de **responsabilidade**, o usuário será solicitado a inserir um local manualmente.

Para configurar o banco de dados de localização, você executará as seguintes tarefas:

1.  Preencha o banco de dados com um mapeamento de elementos de rede para os locais. Se você usar um gateway de número de identificação de localização de emergência (ELIN), precisará incluir o \<Elin\> no campo CompanyName.

2.  Valide os endereços em relação ao MSAG (catálogo de endereços principal) mantido pelo provedor de serviços de emergência.

3.  Publique o banco de dados atualizado.

<div>


> [!NOTE]  
> Como alternativa, você pode definir um banco de dados de origem de local secundário que pode ser usado no banco de dados de localização. Para obter detalhes, consulte <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurar um serviço de informações de localização secundário no Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Preencher o banco de dados de localização no Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Validar endereços no Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Publicar o banco de dados de localização do Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

