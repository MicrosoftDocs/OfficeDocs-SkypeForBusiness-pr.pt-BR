---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4245efe0faf5dfe947cc52fb22a447e46c0b3e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751253"
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

Este tópico destaca as definições de configuração que você deve estar ciente antes da implantação do servidor de borda do Lync Server 2013. Esta seção destaca somente os principais pontos a serem considerados como parte da implantação do seu pool de Borda piloto. Para obter etapas detalhadas, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para acesso de usuário externo.

Conforme você navega pelo assistente **Definir Novo Pool de Borda**, reveja as principais definições de configuração exibidas nas etapas a seguir. Observe que somente algumas páginas do assistente **Definir Novo Pool de Borda** são mostradas.

**Definir um Pool de Borda**

1.  Abra a topologia do pool piloto usando o Construtor de Topologia

2.  Navegue até o nó do Lync Server 2013. Clique com o botão direito em **Pools de borda** e clique em **Novo pool de borda**.
    
    ![Caixa de diálogo Definir novo pool de borda](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda")

3.  Um pool de Borda pode ser um **Pool de vários computadores** ou **Pool de computador único**.
    
    ![Caixa de diálogo definir o FQDN do pool de borda](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Caixa de diálogo definir o FQDN do pool de borda")

4.  Na página **Selecionar recursos**, não habilite a federação ou a federação XMPP. Atualmente, a Federação e a Federação do XMPP são roteadas através do servidor de borda herdado do Office Communications Server 2007 R2. Estes recursos são configurados em uma fase posterior da migração.
    
    ![Caixa de diálogo Selecionar recursos](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")

5.  Em seguida, continue preenchendo as seguintes páginas do assistente: **Selecionar opções de IP**, **FQDNs Externos**, **Definir um endereço IP interno** e **Definir um endereço IP externo**.

6.  Na página **definir o próximo salto** , selecione o diretor do próximo salto do pool de borda do Lync Server 2013.
    
    ![Caixa de diálogo Definir novo pool de borda, lista de pool de próximo salto](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda, lista de pool de próximo salto")

7.  Na página **associar pools de front-ends** , não associe um pool a este pool de borda neste momento. No momento, o tráfego de mídia externo é roteado através do servidor de borda do Office Communications Server 2007 R2 herdado. Esta definição será configurada em uma fase posterior de migração.
    
    ![Caixa de diálogo Definir novo pool de borda](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Caixa de diálogo Definir novo pool de borda")

8.  Clique em **Concluir** e **Publique** a topologia.

9.  Siga as etapas em [instalar servidores de borda para o Lync Server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.

É muito importante que você siga as diretrizes nos tópicos que [implantam o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação. Esta seção forneceu somente algumas informações sobre definições de configuração ao instalar estas funções de servidor.

Agora você deve ter uma implantação herdada do servidor de borda do Office Communications Server 2007 R2, indicada pela presença do BackCompatSite, em paralelo com uma implantação do servidor de borda do Lync Server 2013. A Federação é configurada para usar o diretor do Office Communications Server 2007 R2. Verifique se ambas as implantações estão em execução adequadamente, se os serviços foram iniciados e se é possível administrar cada implantação antes de seguir para a próxima fase.

![Construtor de topologia mostrando o servidor de borda do OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Construtor de topologia mostrando o servidor de borda do OCS")

</div>

<span> </span>

</div>

</div>

</div>

