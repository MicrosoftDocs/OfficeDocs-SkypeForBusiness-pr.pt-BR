---
title: Configurar os servidores de aplicativos confiáveis
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535d5d9a34d450c964300e9caaa16c6b80734732
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurar os servidores de aplicativos confiáveis

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-11_

Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o pool de próximo salto como um pool do Lync Server 2013. Em um ambiente misto, o pool herdado do Lync Server 2010 e o pool 2013 do Lync Server aparecem na lista suspensa. Selecionar o pool herdado não é suportado.

**Selecionar Lync Server 2013 como próximo salto ao criar um servidor de aplicativos confiáveis**

1.  Abra o Construtor de Topologia.

2.  No painel esquerdo, clique com o botão direito em **Servidores de aplicativos confiáveis** e clique em **Novo pool de aplicativo confiável**.

3.  Insira o **FQDN do Pool** do pool de aplicativos confiáveis e selecione se será um servidor múltiplo ou único.

4.  Clique em **Avançar**.

5.  Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Lync Server 2013.

6.  Clique em **Concluir**.

7.  Selecione o nó superior **Lync Server** e no menu **Ações**, selecione **Publicar**.
    
    Verifique se o **Pool de Aplicativos Confiáveis ** foi criado com êxito e estará associado ao pool de Front-End correto.

</div>

<span> </span>

</div>

</div>

</div>

