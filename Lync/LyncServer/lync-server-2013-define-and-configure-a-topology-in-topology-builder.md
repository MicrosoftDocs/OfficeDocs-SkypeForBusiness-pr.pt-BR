---
title: 'Lync Server 2013: Definir e configurar uma topologia no Construtor de Topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Definir e configurar uma topologia no Construtor de Topologia para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Executar o construtor de topologias para definir uma nova topologia ou modificar uma topologia existente não requer associação em um administrador local ou em um grupo de domínio privilegiado. O construtor de topologias orienta você pelas etapas necessárias para definir sua topologia para um pool Front-end do Enterprise Edition ou uma edição padrão, com base em seus requisitos de configuração.

Você deve usar o construtor de topologias para concluir e publicar a topologia antes de poder instalar o Lync Server 2013 em servidores. O procedimento a seguir inclui as etapas necessárias para definir uma nova topologia.

<div>

## <a name="to-define-a-topology"></a>Para definir uma topologia

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Em Construtor de topologia, selecione **nova topologia**. Você será solicitado a fornecer um local e um nome de arquivo para salvar a topologia. Dê ao arquivo de topologia um nome significativo e aceite a extensão padrão de. tbxml. Clique em **OK**.

3.  Navegue até o local onde você deseja salvar o novo arquivo XML de topologia, insira um nome para o arquivo e clique em **salvar**.

4.  Na página **definir o domínio primário** , digite o nome do domínio SIP principal da sua organização e clique em **Avançar**.

5.  Na página **especificar outros domínios com suporte** , insira os nomes de domínios adicionais, se houver, e clique em **Avançar**.

6.  Na página **definir o primeiro site** , insira um nome e uma descrição para o primeiro site e clique em **Avançar**.

7.  Na página **especificar detalhes do site** , insira as informações de localização do site e clique em **Avançar**.

8.  Na página **nova topologia definida com êxito** , certifique-se de que a caixa de seleção **abrir o assistente de novo front-end quando este assistente for fechado** estiver marcada e clique em **concluir**.

Depois de definir e salvar a topologia, use o novo assistente de front-end para definir um pool de front-end ou um servidor Standard Edition para seu site. Para obter detalhes, consulte [definir e configurar um pool de front-end ou um servidor Standard Edition no Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

