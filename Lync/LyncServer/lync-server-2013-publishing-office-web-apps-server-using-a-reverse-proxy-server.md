---
title: Publicando o servidor do Office Web Apps usando um servidor de proxy reverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>Publicando o servidor do Office Web Apps no Lync Server 2013 usando um servidor proxy reverso

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-25_

Se você quiser que os usuários externos (ou seja, os usuários que estão fazendo logon fora do firewall da sua organização) tenham acesso às apresentações do PowerPoint para servidor Web Apps do Office, será necessário usar o Office Web Apps Server e um servidor proxy reverso, como o Microsoft Forefront Gateway de gerenciamento de ameaças. Isso também significa que você vai precisar criar e configurar uma regra de publicação de site; Essa regra ajudará a garantir que os usuários possam se conectar ao servidor. Se você não precisar fornecer acesso a usuários externos, não será necessário configurar uma regra de publicação de site.

Para configurar uma regra de publicação de site no Forefront Threat Management Gateway, conclua o seguinte procedimento:

1.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Forefront TMG**e, em seguida, clique em gerenciamento do **Forefront TMG**.

2.  No Forefront TMG, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.

3.  No Assistente para nova regra de publicação na Web, na página **Bem-vindo ao novo assistente de regra de publicação na Web** , digite um nome para a nova regra na caixa **nome da regra de publicação na Web** (por exemplo, regra do servidor do **Office Web Apps**) e clique em **Avançar**.

4.  Na página **especificar ação da regra** , selecione **permitir** e clique em **Avançar**.

5.  Na página **tipo de publicação** , selecione **publicar um único site ou balanceador de carga** e, em seguida, clique em **Avançar**.

6.  Na página **segurança de conexão do servidor** , selecione **usar SSL para se conectar ao servidor Web ou ao farm de servidores publicados** e clique em **Avançar**.

7.  Na página **detalhes da publicação interna** , digite o FQDN do servidor do Office Web Apps (por exemplo, **officewebapps01.contoso.com**) na caixa **nome do site interno** e clique em **Avançar**. O nome inserido na caixa **nome do site interno** deve aparecer no campo assunto ou no campo nome alternativo do assunto do certificado que você atribuiu ao servidor do Office Web Apps.

8.  Na página **detalhes da publicação interna** , digite ** / ** na caixa **caminho (opcional)** e, em seguida, clique em **Avançar**. A sintaxe\* /irá ajudar a garantir que todas as pastas e subpastas do site sejam publicadas.

9.  Na página de **detalhes do nome público** , selecione **este nome de domínio (Digite abaixo)** na lista de **aceitar solicitações para** e digite o totalmente qualificado para o servidor do Office Web Apps na caixa nome público. Esse nome deve ser o nome usado para acessar seu site. Por exemplo, se o seu site for acessado http://officewebapps01.contoso.com usando a URL, você deverá digitar **officewebapps01.contoso.com** na caixa **nome público** .

10. Click **Next**.

11. Na página **selecionar ouvinte da Web** , clique em **novo**.

12. No assistente de definição novo ouvinte da Web, digite um nome para o novo ouvinte da Web (por exemplo, **SSL**) na caixa **nome do ouvinte da Web** e, em seguida, clique em **Avançar**.

13. Na página **segurança de conexão do cliente** , selecione **exigir conexões SSL seguras com clientes** e, em seguida, clique em **Avançar**.

14. Na página **endereços IP do ouvinte da Web** , selecione **externo**, selecione **interno**e clique em **Avançar**.

15. Na página **certificados SSL de ouvinte** , selecione **usar um único certificado para este ouvinte da Web** e clique em **Selecionar certificado**.

16. Na caixa de diálogo **Selecionar certificado** , selecione o certificado a ser usado para este ouvinte da Web e clique em **selecionar**.

17. Na página **certificados SSL de ouvinte** , clique em **Avançar**.

18. Na página **configurações de autenticação** , selecione **sem autenticação** na lista suspensa **selecionar como os clientes fornecerão credenciais para a** lista suspensa do Forefront TMG e clique em **Avançar**.

19. Na página **configurações de logon único** , clique em **Avançar**.

20. Na página **concluindo o assistente de Nova escuta da Web** , examine o resumo das opções de configuração que você fez. Quando estiver pronto, clique em **concluir**.

21. Na página **selecionar ouvinte da Web** , clique em **Avançar**.

22. Na página **delegação de autenticação** , selecione **sem delegação, mas o cliente pode autenticar diretamente** da **seleção do método usado pelo Forefront TMG para autenticação na lista suspensa do servidor Web publicado** e, em seguida, clique em **Avançar**.

23. Na página **conjuntos de usuários** , confirme se os conjuntos de usuários apropriados estão listados. Por padrão, esse é o conjunto de **usuários todos os usuários** . Clique em **Adicionar** para adicionar outros conjuntos de usuários que você tenha definido. Quando concluir, clique em **Avançar**.

24. Na página **concluindo o assistente de nova regra de publicação na Web** , clique em **concluir**.

Observe que clicar em **concluir** não significa que você concluiu o processo; Isto é, isso não aplica e habilita automaticamente a nova regra. Em vez disso, você precisará clicar no botão **aplicar** que será exibido na interface do usuário do Forefront TMG. Quando você clica em **aplicar** a caixa de diálogo **Descrição da alteração de configuração** será exibida. Clique em **aplicar** nessa caixa de diálogo para habilitar a nova regra de publicação.

Após a aplicação da nova regra, você precisará fazer algumas pequenas modificações na regra para garantir que os usuários possam usar os novos recursos de apresentação do PowerPoint. Para fazer isso, siga este procedimento:

1.  No Forefront TMG, clique com o botão direito do mouse no nome da nova regra de publicação e, em seguida, clique em **Propriedades**.

2.  Na caixa de diálogo **Propriedades** , na guia **para** , selecione a opção **encaminhar o cabeçalho original do host, em vez do verdadeiro**.

3.  Na guia **tráfego** , clique em **filtragem** e, em seguida, clique em **Configurar http**.

4.  Na caixa de diálogo **Configurando a política http para a regra** , desmarque a caixa de seleção **verificar normalização** e clique em **OK**.

5.  Na caixa de diálogo **Propriedades** , clique em **OK**.

6.  No Forefront TMG, clique em **aplicar** para habilitar as alterações. Quando a caixa de diálogo **Descrição da alteração de configuração** for exibida, clique em **aplicar**.

Depois de concluir a instalação, você pode testar o servidor do Office Web Apps usando os procedimentos no tópico [validando a configuração do servidor do Office Web Apps no Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).

</div>

<span> </span>

</div>

</div>

</div>

