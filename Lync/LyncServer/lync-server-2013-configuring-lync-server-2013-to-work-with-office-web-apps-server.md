---
title: Configurando o Lync Server 2013 para funcionar com o servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2043c974654ba2a65b3d831cd65fef420e4b5708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Configurando o Lync Server 2013 para funcionar com o servidor do Office Web Apps

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-04-22_

Antes de poder configurar o Lync Server 2013 para usar o servidor do Office Web Apps, o servidor do Office Web Apps deve ser implantado e configurado. Consulte o documento **Guia para implantar o Servidor Office Web Apps e o Office Web Apps** para obter informações detalhadas sobre como instalar e configurar um único Servidor Office Web Apps ou um farm de Servidores Office Web Apps para alta disponibilidade.

Após o servidor do Office Web Apps ter sido instalado com êxito e seu farm da Web corretamente configurado, você deve configurar o Lync Server para se comunicar com o novo servidor; Isso é feito adicionando a URL de descoberta do Office Web Apps Server à sua topologia do Lync Server. Para adicionar o servidor do Office Web Apps à sua topologia, conclua as seguintes etapas:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar Topologia da implantação existente** e clique em **OK**.

3.  Na caixa de diálogo **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.

4.  No construtor de topologias, expanda **Lync Server 2013**, expanda o nome do seu site, expanda **pools de front-ends Enterprise Edition**, clique com o botão direito do mouse no nome de um dos seus pools e clique em **Editar propriedades**.

5.  Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor Office Web Apps** e clique em **Novo** (ou selecione um Servidor Office Web Apps existente na lista suspensa).

6.  Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor Office Web Apps na caixa **FQDN do Servidor Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor Office Web Apps**.
    
    Se o servidor do Office Web Apps estiver instalado no local e na mesma zona de rede do Lync Server 2013, a opção **Office Web Apps Server é implantada em uma rede externa (ou seja, perímetro/Internet)** não deve ser selecionada.
    
    Se o Servidor Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.

7.  Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e depois em **OK** na caixa de diálogo **Editar Propriedades**. Em seguida, a URL de descoberta do Office Web Apps será listada como uma das associações do pool.

Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor Office Web Apps.

Depois que você adicionar a URL de descoberta à topologia, terá que publicar a topologia atualizada. Para isso, no Construtor de Topologias:

1.  Clique em **Ação** e depois em **Publicar Topologia**.

2.  No assistente Publicar Topologia, na página **Publicar a topologia**, clique em **Avançar**.

3.  Na página **Assistente de publicação concluído**, clique em **Concluir**.

4.  Feche o Construtor de Topologias.

</div>

<span> </span>

</div>

</div>

</div>

