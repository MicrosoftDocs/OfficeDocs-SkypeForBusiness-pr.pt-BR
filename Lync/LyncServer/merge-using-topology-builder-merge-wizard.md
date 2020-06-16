---
title: Mesclar usando o assistente de mesclagem do construtor de topologia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>Mesclar usando o assistente de mesclagem do construtor de topologia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

1.  Baixar a implantação existente utilizando o Construtor de Topologia.

2.  No menu **Ação**, selecione **Mesclar o Office Communications Server 2007 R2**.

3.  Clique em **Avançar**.

4.  Em **Especificar Configuração de Borda**, clique em **Adicionar**.
    
    ![Assistente de topologia de mesclagem, especificar página de configuração de borda](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistente de topologia de mesclagem, especificar página de configuração de borda")  

5.  In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**. This example uses the **Single Edge Server** option.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Expanded Edge deployment</STRONG> is not a supported configuration. An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.

    
    </div>

6.  Em **especificar configurações de borda interna** , insira as informações relevantes para o FQDN interno e as portas do seu pool de borda conforme necessário e clique em **Avançar**.
    
    ![Caixa de diálogo especificar configurações de borda interna](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Caixa de diálogo especificar configurações de borda interna")  

7.  Em **Especificar Borda Externa**, insira as informações de FQDN de conferência da Web do seu Servidor de Borda.
    
    <div>
    

    > [!IMPORTANT]  
    > Before you click <STRONG>Next</STRONG>, do the next step in this procedure. It is very important that you do not miss this step.

    
    </div>

8.  Marque a caixa de seleção **este pool de borda é usado para Federação e conectividade de im pública** se você planeja usar o servidor de borda do Office Communications Server 2007 R2 herdado para Federação. Se você possui vários Servidores de Borda implantados, somente um deles ficará habilitado para federação. Se você não marcar essa caixa e depois decidir que quer habilitar a federação, deve executar o assistente de Mesclagem de Construtor de Topologia novamente e depois publicar sua topologia novamente.
    
    ![Caixa de diálogo servidor de borda, especificar página de borda externa](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Caixa de diálogo servidor de borda, especificar página de borda externa")  

9.  Em **Especificar próximo salto**, insira o FQDN do próximo salto em seu ambiente. Clique em **Finalizar**.
    
    ![Caixa de diálogo servidor de borda, especificar página de próximo salto](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Caixa de diálogo servidor de borda, especificar página de próximo salto")  

10. Em **especificar configuração de borda**, se todos os servidores de borda do Office Communications Server 2007 R2 tiverem sido adicionados, clique em **Avançar**. Se você tiver mais servidores de borda do Office Communications Server 2007 R2 para adicionar, repita este procedimento a partir da etapa 4.

11. Em **especificar porta SIP interna** , selecione a configuração padrão (ou seja, se você não modificou a porta SIP padrão). Faça as alterações conforme seja apropriado se você não estiver usando uma porta padrão de 5061 e clique em **Avançar**.

12. Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.

13. A página do assistente verifica se a mesclagem das topologias foi bem-sucedida.

14. Na coluna **Status**, verifique se o valor é **Êxito** e clique em **Finalizar**.

15. No painel esquerdo do construtor de topologia, você deve ver agora o **BackCompatSite**, que indica que seu ambiente do Office Communications Server 2007 R2 foi mesclado com o Lync Server 2013.
    
    ![Construtor de topologia mostrando uma topologia mesclada](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Construtor de topologia mostrando uma topologia mesclada")  

16. No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.

17. Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > É importante que você conclua o próximo tópico, <A href="import-policies-and-settings.md">importar políticas e configurações</A>, para garantir que as configurações da política herdada sejam importadas para o Lync Server 2013.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

