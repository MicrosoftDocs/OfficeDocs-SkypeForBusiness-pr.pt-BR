---
title: Configurando o Lync Server 2013 para trabalhar com o servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Configurando o Lync Server 2013 para trabalhar com o servidor do Office Web Apps

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-04-22_

Antes de poder configurar o Lync Server 2013 para usar o Office Web Apps Server, o Office Web Apps Server deve ser implantado e configurado. Consulte o guia do documento **para implantar o Office Web Apps Server e os Office Web Apps** para obter informações detalhadas sobre como instalar e configurar um único servidor do Office Web Apps ou para obter informações sobre como instalar e configurar um Office Web Apps Server farm para alta disponibilidade.

Após a instalação bem-sucedida do Office Web Apps Server e sua Web farm configurada corretamente, você deve configurar o Lync Server para se comunicar com o novo servidor; Isso é feito adicionando-se a URL de descoberta do servidor do Office Web Apps à sua topologia do Lync Server. Para adicionar o Servidor do Office Web Apps à sua topologia, execute estas etapas:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.

3.  Na caixa de diálogo  **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa  **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.

4.  No construtor de topologias, expanda o **Lync Server 2013**, expanda o nome do seu site, expanda Pools de **front-end do Enterprise Edition**, clique com o botão direito do mouse no nome de um dos seus pools e clique em **Editar propriedades**.

5.  Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor do Office Web Apps** e clique em **Novo** (ou selecione um Servidor do Office Web Apps existente na lista suspensa).

6.  Na caixa de diálogo **Definir Novo Servidor do Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor do Office Web Apps na caixa **FQDN do Servidor do Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor do Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor do Office Web Apps**.
    
    Se o Office Web Apps Server estiver instalado no local e na mesma zona de rede do Lync Server 2013, a opção **Office Web Apps Server será implantada em uma rede externa (isto é, perímetro/Internet)** não deve ser selecionada.
    
    Se o Servidor do Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.

7.  Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e em **OK** na caixa de diálogo **Editar Propriedades**. A URL de descoberta do Office Web Apps será então listada como uma das associações do pool.

Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor do Office Web Apps.

Depois de adicionar a URL de descoberta à topologia, você deve publicar essa topologia atualizada. Para isso, no Construtor de Topologias:

1.  Clique em **Ação** e depois em **Publicar Topologia**.

2.  No assistente Publicar topologia, na página **Publicar a Topologia**, clique em **Avançar**.

3.  Na página **Assistente de publicação concluído**, clique em **Concluir**.

4.  Feche o Construtor de Topologias.

</div>

<span> </span>

</div>

</div>

</div>

