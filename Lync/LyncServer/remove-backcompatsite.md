---
title: Remover BackCompatSite
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 792fcf29033a7495a7da340decb561e25084612d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Remover BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Depois que todos os pools estão desativados e todos os Servidores de Borda desinstalados, execute o assistente de Mesclagem do Construtor de Topologia para remover o **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Para remover o site BackCompat do Construtor de Topologia

1.  Abra uma implantação existente  do Construtor de Topologia.

2.  No menu **Ação**, clique em **Mesclar Topologia R2 2007**.

3.  Clique em **Avançar** para continuar.

4.  On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.
    
    ![Assistente de topologia de mesclagem, especificar página de configuração de borda](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistente de topologia de mesclagem, especificar página de configuração de borda")  

5.  Na página **Especificar configuração da porta SIP interna**, clique em **Avançar**.

6.  Na página **Resumo** , clique em **Avançar** para começar a mesclar as topologias para remover o site herdado.

7.  Na coluna **Status**, verifique se o valor está como **Sucesso** e, então, clique em **Concluir** para fechar o assistente.

8.  No painel à esquerda do Construtor de Topologia, expanda o BackCompatSite e certifique-se que não há servidores listados.

9.  Clique com o botão direito do mouse em **BackCompatSite** e cliquem, então, em **Excluir**.

10. No **Construtor de Topologia**, selecione o nó superior **Servidor Lync**.

11. No menu **Ação**, selecione **Publicar Topologia** e clique em **Avançar**.

12. Quando o **Assistente para Publicação** for concluído, clique em **Concluir ** para fechar o assistente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

