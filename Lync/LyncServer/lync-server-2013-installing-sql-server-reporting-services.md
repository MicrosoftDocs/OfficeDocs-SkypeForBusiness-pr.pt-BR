---
title: 'Lync Server 2013: Instalando o SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9044f90146b604f0277b0a5b815c6540849d58b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534928"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Instalando o SQL Server Reporting Services no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-20_

Se você pretende usar os relatórios de monitoramento do Microsoft Lync Server 2013 (consulte a próxima seção desta documentação para obter mais informações), primeiro é necessário instalar o SQL Server Reporting Services; O Reporting Services pode ser instalado ao mesmo tempo em que você instala o Microsoft SQL Server ou a qualquer momento após a instalação do SQL Server. Se você não tiver instalado o SQL Server, siga as instruções fornecidas anteriormente nesta documentação. Ao instalar o SQL Server, certifique-se de que, na página seleção de recursos, você seleciona o Reporting Services. Isso instalará o SQL Server Reporting Services.

Se você já instalou o SQL Server, mas não o SQL Server Reporting Services, poderá adicionar esse recurso seguindo as instruções correspondentes ao SQL Server 2008 R2 ou ao SQL Server 2012, dependendo da versão desejada.

Para verificar se o Reporting Services foi instalado com êxito, execute as etapas a seguir:

1.  Se estiver executando o Microsoft SQL Server 2008 R2, clique em **Iniciar**, em **Todos os Programas**, em **Microsoft SQL Server 2008 R2**, em **Ferramentas de Configuração** e depois em **Gerenciador de Configuração do Reporting Services**.
    
    Se estiver executando o Microsoft SQL Server 2012, clique em **Iniciar**, em **Todos os Programas**, em **Microsoft SQL Server 2012**, em **Ferramentas de Configuração** e depois em **Gerenciador de Configuração do Reporting Services**.

2.  Na caixa de diálogo **Conexão de Configuração do Reporting Services**, verifique se o nome do seu servidor aparece na caixa **Nome do Servidor** e se o nome da instância do SQL Server que armazena seus dados de monitoramento aparece na caixa **Instância do Servidor de Relatório**. Clique em **Conectar**.

No Gerenciador de configuração do Reporting Service, o painel de status do servidor de relatório deve mostrar que o SQL Server Reporting Services foi instalado e que o Reporting Services está sendo executado: o status do servidor de relatório deve ser mostrado como **iniciado** e o botão **Iniciar** deve estar esmaecido e indisponível. Se o Reporting Services não estiver em execução, clique em **Iniciar** para iniciar o serviço.

Se nenhum banco de dados estiver listado ao lado do rótulo Nome do Banco de Dados do Servidor de Relatório, faça o seguinte:

1.  No Gerenciador de Configuração do Reporting Services, clique em **Banco de dados**.

2.  No painel Banco de Dados do Servidor de Relatório, clique em **Alterar Banco de Dados**.

3.  No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Ação, selecione **Criar um novo banco de dados do servidor de relatório** e clique em **Avançar**.

4.  No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Servidor de Banco de Dados, verifique se as informações listadas nas caixas **Nome do Servidor**, **Tipo de Autenticação** e **Nome de Usuário** estão corretas. Clique em **Testar Conexão** para verificar se é possível estabelecer uma conexão com o servidor de banco de dados e clique em **Avançar**.

5.  No Assistente de Configuração do Banco de Dados do Servidor de Relatório, aceite os valores padrão para **Nome do Banco de Dados**, **Idioma** e **Modo do Servidor de Relatório** e clique em **Avançar**.

6.  No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Credenciais, verifique se as informações corretas constam na lista suspensa **Tipo de Autenticação** e nas caixas **Nome de Usuário** e **Senha** e clique em **Avançar**.

7.  No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Resumo, clique em **Avançar**.

8.  No Assistente de Configuração do Banco de Dados do Servidor de Relatório, no painel Progresso e Conclusão, clique em **Concluir**.

Para verificar se as URLs do Reporting Services estão configuradas, clique em **URL do Serviço Web**. Você deverá ver uma ou mais URLs listadas sob o cabeçalho **URLs do Serviço Web Servidor de Relatórios**. Clique em cada uma dessas URLs para verificar se consegue acessar a home page da instalação local do SQL Server Reporting Services.

</div>

<span> </span>

</div>

</div>

</div>

