---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba616f6a5ce86e0f94c3b52afd60aaba34b7635
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Implantar um Servidor de Borda piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Este tópico destaca as definições de configuração que você deve estar ciente antes da implantação do servidor de borda do Lync Server 2013. Os processos de implantação e configuração do Lync Server 2013 são muito semelhantes aos do Lync Server 2010. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. Para obter etapas detalhadas, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para acesso de usuário externo.

As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.

**Definir um Pool de Borda**

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Navegue até o nó do Lync Server 2013. Clique com o botão direito em **Pools de borda** e clique em **Novo pool de borda**.
    
    ![Caixa de diálogo Definir novo pool de borda](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda")

3.  Um pool de Borda pode ser um **Pool de vários computadores** ou **Pool de computador único**.
    
    ![Caixa de diálogo definir o FQDN do pool de borda](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Caixa de diálogo definir o FQDN do pool de borda")

4.  Na página **Selecionar recursos**, não habilite a federação ou a federação XMPP. A Federação e a Federação XMPP são roteadas atualmente através do servidor de borda do Lync Server 2010 herdado. Estes recursos são configurados em uma fase posterior da migração.
    
    ![Caixa de diálogo Selecionar recursos](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")

5.  Em seguida, continue preenchendo as seguintes páginas do assistente: **FQDN's Externos**, **Definir o endereço IP interno** e **Definir o endereço IP externo**.

6.  Na página **definir o próximo salto** , selecione o diretor do próximo salto do pool de borda do Lync Server 2010.
    
    ![Caixa de diálogo Definir próximo salto](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Caixa de diálogo Definir próximo salto")

7.  Na página **associar pools de front-ends ou de mediação** , não associe um pool a este pool de borda neste momento. No momento, o tráfego de mídia externo é roteado através do servidor de borda do Lync Server 2010 herdado. Esta definição será configurada em uma fase posterior de migração.
    
    ![Caixa de diálogo associar pools de front-ends](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Caixa de diálogo associar pools de front-ends")

8.  Clique em **Concluir** e **Publique** a topologia.

9.  Siga as etapas em [instalar servidores de borda para o Lync Server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.

É muito importante que você siga as diretrizes nos tópicos que [implantam o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação. Esta seção forneceu somente algumas informações sobre definições de configuração ao instalar estas funções de servidor.

Agora você deve ter um servidor de borda do Lync Server 2010 herdado implantado em paralelo com uma implantação do servidor de borda do Lync Server 2013. Verifique se ambas as implantações estão em execução adequadamente, se os serviços foram iniciados e se é possível administrar cada implantação antes de seguir para a próxima fase.

</div>

<span> </span>

</div>

</div>

</div>

