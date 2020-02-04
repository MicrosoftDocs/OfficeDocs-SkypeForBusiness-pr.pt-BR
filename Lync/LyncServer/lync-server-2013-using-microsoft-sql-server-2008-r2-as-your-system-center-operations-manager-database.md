---
title: 'Lync Server 2013: usando o Microsoft SQL Server 2008 R2 como seu banco de dados do System Center Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Usar o Microsoft SQL Server 2008 R2 como seu banco de dados do System Center Operations Manager para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-29_

Para usar o SQL Server 2008 R2 como seu banco de dados back-end, conclua as etapas detalhadas neste tópico.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configuração do SQL Server 2008 R2 e do SQL Server Reporting Services

Antes de começar a instalar o System Center Operations Manager, você deve fazer duas alterações no SQL Server 2008 R2 e na configuração do SQL Server Reporting Services. (Essas alterações só serão necessárias se você estiver usando o SQL Server 2008 R2 como seu banco de dados do Operations Manager.) Primeiro, faça o seguinte no computador que hospedará seu banco de dados do Operations Manager:

1.  Clique em **Iniciar** e em **executar**.

2.  Na caixa de diálogo **executar** , digite **C:\\\\Program Files Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting Services\\ReportServer** e pressione Enter.

3.  Na pasta **ReportServer** , abra o arquivo **RSReportServer. config** no bloco de notas ou qualquer outro editor de texto.

4.  Próximo ao início do arquivo, você verá uma série de nós "Adicionar chave". Localize a entrada que começa ** \<a adicionar Key = "SecureConnectionLevel"** e defina o valor como **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Salve o arquivo **RSReportServer. config** e, em seguida, feche o editor de texto.

Após atualizar o arquivo de configuração do Report Server, você deve atribuir o certificado correto ao SQL Server Reporting Services. Para fazer isso:

1.  Clique em **Iniciar**, **em todos os programas**, em **Microsoft SQL Server 2008 R2**, em **ferramentas de configuração**e em Gerenciador de configuração do **Reporting Services**.

2.  Na caixa de diálogo **conexão de configuração do Reporting Services** , verifique se o nome do seu servidor é exibido na caixa **nome do servidor** . Selecione a instância do SQL Server que hospedará seu banco de dados do Operations Manager (por exemplo, **ARCHINST**) na lista suspensa de **instâncias do servidor de relatório** e clique em **conectar**.

3.  No Gerenciador de configuração do Reporting Services, clique em **URL do serviço Web**.

4.  Na página **Web Service URL** , selecione o certificado a ser usado para o Reporting Services da lista suspensa **certificado SSL** e clique em **aplicar**. Após alguns segundos, você verá um par de URLs listadas nas **URLs do serviço Web do Report Server**.

5.  Clique em ambas as URLs para verificar se você pode acessar o SQL Server Reporting Services.

6.  Feche o Gerenciador de configuração do Reporting Services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Criando um banco de dados do System Center Operations Manager para uso com o SQL Server 2008 R2

Se você quiser configurar o System Center Operations Manager para usar um banco de dados do SQL Server 2008 R2, será necessário "manualmente" criar o banco de dados do Operations Manager no computador que executa o SQL Server 2008 R2. (Novamente, essas etapas não serão necessárias se você estiver usando o SQL Server 2005 ou o SQL Server 2008 como seu banco de dados back-end.)

Para criar manualmente um banco de dados do Operations Manager, faça o seguinte:

1.  Na mídia de instalação do System Center Operations Manager 2007 R2, na\\pasta SupportTools AMD64, clique duas vezes em **DBCreateWizard. exe**.

2.  No assistente de configuração de banco de dados, na página **Bem-vindo ao assistente de configuração de banco de dados** , clique em **Avançar**.

3.  Na página **informações do banco de dados** saia de todas as configurações e clique em **Avançar** .

4.  Na página **configuração do grupo de gerenciamento** digite um nome para o seu grupo de gerenciamento (por exemplo, **monitoração do Lync Server**) na caixa **nome do grupo de gerenciamento** e clique em **Avançar**.

5.  Na página **relatórios de erros do Operations Manager** , clique em **Avançar**.

6.  Na página **Resumo** , clique em **concluir**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Criando um data warehouse do System Center Operations Manager para uso com o SQL Server 2008 R2

O Microsoft Lync Server 2013 vem com três novos relatórios do System Center Operations Manager:

  - **Relatório de disponibilidade do cenário de ponta a ponta**   este relatório detalha a disponibilidade/tempo de atividade dos serviços principais do Lync Server, como registro ou presença.

  - **Relatório de capacidade**   usando informações de contador de desempenho, esse relatório mostra tendências para componentes do sistema, como disponibilidade da memória e uso do processador.

  - **Relatório de componente**   este relatório lista os principais geradores de alertas agrupados pelo componente do Lync Server.

Para usar esses novos relatórios, você deve instalar um data warehouse do System Center Operations Manager. (Um depósito de dados permite armazenamento de longo prazo de dados de operações.) Para usar um data warehouse com o SQL Server 2008 R2, você deve executar as seguintes etapas no computador que hospeda seu banco de dados do SQL Server:

1.  Na mídia de instalação do System Center Operations Manager, na\\pasta\\setup SupportTools AMD64, clique duas vezes em **DBCreateWizard. exe**.

2.  No assistente de configuração de banco de dados, na página **Bem-vindo ao assistente de configuração de banco de dados** , clique em **Avançar**.

3.  Na página **informações do banco** de dados, selecione o **banco de dados de data warehouse do Operations Manager** na lista suspensa **tipo de banco** de dados e clique em **Avançar**.

4.  Na página **Resumo** , clique em **concluir**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Instalando o console do System Center Operations Manager

O console do Operations Manager é a principal ferramenta usada para gerenciar o System Center Operations Manager. Antes de instalar o console do Operations Manager, verifique se você instalou uma versão com suporte do SQL Server, juntamente com o serviço relatórios do SQL Server. Também é recomendável que você execute o Gerenciador de configuração do Reporting Services do SQL Server para verificar se o serviço de relatório foi instalado e configurado corretamente.

Para instalar o console do System Center Operations Manager:

1.  Na mídia de instalação do System Center Operations Manager, clique duas vezes em **SetupOM. exe**.

2.  Na configuração do System Center Operations Manager 2007 R2, clique em **verificar pré-requisitos**.

3.  No Visualizador de pré-requisitos do System Center Operations Manager, selecione os componentes do System Center a serem instalados: (**servidor**; **Console**; e do **PowerShell**) e clique em **verificar**. Verifique se não foram relatados problemas de bloqueio e clique em **fechar**. Se um problema de bloqueio tiver sido reportado, corrija o problema e clique em **verificar** para executar novamente o teste de pré-requisito.

4.  Na instalação do System Center Operations Manager, clique em **instalar Gerenciador de operações**.

5.  No assistente de configuração do System Center Operations Manager, na página **Bem-vindo ao assistente de configuração do System Center Operations Manager** , clique em **Avançar**.

6.  Na página de **contrato de licença de usuário final** , selecione **aceito os termos do contrato de licença** e clique em **Avançar**.

7.  Na página **registro de produto** , digite seu nome na caixa **nome de usuário** e o nome da sua organização na caixa **organização** . Digite a chave do produto (Product Key) do System Center Operations Manager na caixa **digite a chave do CD de 25 dígitos** e clique em **Avançar**.

8.  Na página **configuração personalizada** , selecione as opções do System Center a serem instaladas e clique em **Avançar**. Você deve selecionar **servidor de gerenciamento**, **interfaces do usuário**e **console Web** para ser instalado. O **banco de dados** não deve ser selecionado e não deve ser instalado.

9.  Na página **instância do servidor de banco de dados SC** , verifique se o nome do computador em que os bancos de dados do Operations Manager estão instalados aparece na caixa **servidor de banco de dados do System Center** . Click **Next**.

10. Na página da **conta de ação do servidor de gerenciamento** , selecione conta de **domínio ou computador local** e, em seguida, insira os valores apropriados nas caixas conta de **usuário**, **senha**e **domínio ou computador local** . Click **Next**.

11. Na página **da conta do serviço SDK e config** , selecione **conta de domínio ou computador local** e, em seguida, insira os valores apropriados nas caixas **conta de usuário**, **senha**e **domínio ou computador local** . Click **Next**.

12. Na página **relatórios de erros do Operations Manager** , clique em **Avançar**.

13. Na página do **programa de aperfeiçoamento da experiência do usuário** , clique em **Avançar**.

14. Na página **pronto para instalar o programa** , clique em **instalar**.

15. Na página **concluindo a configuração do Gerenciador de operações do System Center** , desmarque a **chave de criptografia de backup** e **inicie as caixas de seleção do console** e clique em **concluir**.

16. Na configuração do System Center Operations Manager, clique em **sair**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Instalar o System Center Reporting Services

Depois de instalar e configurar o console System Center Operations Manager, você deve instalar o System Center Reporting Services. Se você estiver usando o SQL Server 2008 R2 como o banco de dados back-end do Operations Manager, isso significa que você deve primeiro fazer uma alteração temporária no grupo de segurança associado ao SQL Server Reporting Services. Se estiver usando o SQL Server 2008 R2, você deve fazer o seguinte:

1.  Clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciador de servidores**.

2.  No Gerenciador de servidores, expanda **configuração**, expanda **usuários e grupos locais**e clique em **grupos**.

3.  Localize o seguinte grupo, em que ATL-SC-001 representa o nome do seu computador e ARCHINST representa a instância do SQL Server para o banco de dados do System Center: **SQLServerReportServerUser $ ATL-\_SC-001 $ MSRS10 50. ARCHINST**.

4.  Clique com o botão direito do mouse no grupo e clique em **renomear**. Renomeie o grupo excluindo ** \_50** do nome do grupo. Por exemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Feche o Gerenciador de servidores.

Nesse ponto, você está pronto para instalar o System Center Reporting Services. Para fazer isso:

1.  Na mídia de instalação do System Center Operations Manager 2007 R2, clique duas vezes em **SetupOM. exe**.

2.  Na instalação do System Center Operations Manager 2007 R2, clique em **instalar relatório do Operations Manager**.

3.  No assistente de configuração de relatórios do System Center Operations Manager 2007 R2, na página **Bem-vindo à configuração de relatórios do Operations Manager** , clique em **Avançar**.

4.  Na página de **contrato de licença de usuário final** , selecione **aceito os termos do contrato de licença** e clique em **Avançar**.

5.  Na página **registro de produtos** , certifique-se de que seu nome e o nome de sua organização sejam exibidos nas caixas **nome de usuário** e **organização** e, em seguida, clique em **Avançar**.

6.  Na página **configuração personalizada** , clique em **servidor de relatório** e selecione **esse componente, e todos os componentes dependentes serão instalados na unidade de disco local**. Clique em **data warehouse** e selecione **este componente não estará disponível**e, em seguida, clique em **Avançar**.

7.  Na página **conectar-se ao servidor de gerenciamento raiz** , digite o nome do servidor de gerenciamento raiz do Operations Manager na caixa **servidor de gerenciamento raiz** e clique em **Avançar**.

8.  Na página **conectar-se ao data warehouse do Operations Manager** , digite a instância do SQL Server na qual o data warehouse está localizado na caixa **instância do SQL Server** . (Se o seu data warehouse estiver localizado na instância padrão, basta digitar o nome do servidor; por exemplo: ATL-SQL-001.) Verifique se o nome do banco de dados **OperationsManagerDW** aparece na caixa de **nome** e se a porta **1433** é exibida na caixa de **porta do SQL Server** . Click **Next**.

9.  Na página **instância de relatórios do SQL Server** , selecione o servidor de relatórios do SQL Server na lista suspensa **digite o servidor do SQL Server Reporting Services** e clique em **Avançar**.

10. Na página de **gravação da conta de data warehouse** , insira o nome e a senha do usuário para receber as permissões de gravação inicialmente atribuídas ao depósito de dados nas caixas **conta de usuário** e **senha** . Selecione o domínio do usuário na lista suspensa **domínio** e clique em **Avançar**.

11. Na página **conta do leitor de dados** , insira o nome e a senha da conta de usuário a ser usada quando o SQL Reporting Services consulta o armazém de dados nas caixas **conta do usuário** e **senha** . Selecione o domínio de conta na lista suspensa **domínio** e clique em **Avançar**.

12. Na página **relatórios de dados operacionais** , clique em **Avançar**.

13. Na página **Microsoft Update** , clique em **Avançar**.

14. Na página **pronto para instalar o programa** , clique em **instalar**.

15. Na página **concluindo o assistente de configuração dos componentes de relatório do Operations Manager** , clique em **concluir**.

16. Na instalação do System Center Operations Manager 2007 R2, clique em **sair**.

Após a instalação do relatório do System Center, use o procedimento a seguir para redefinir o nome do grupo de segurança associado ao relatório do SQL Server. Novamente, esse procedimento só será necessário se você estiver usando o SQL Server:

1.  Clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciador de servidores**.

2.  No Gerenciador de servidores, expanda **configuração**, expanda **usuários e grupos locais**e clique em **grupos**.

3.  Localize o seguinte grupo, em que ATL-SC-001 representa o nome do seu computador e ARCHINST representa a instância do SQL Server para os bancos de dados de arquivamento e monitoramento: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Clique com o botão direito do mouse no grupo e clique em **renomear**. Renomeie o grupo adicionando ** \_50** ao final do nome do grupo, logo antes do nome da instância do SQL Server. Por exemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Feche o Gerenciador de servidores.

Se o console de operações do System Center estiver aberto, será necessário fechar o aplicativo e reiniciá-lo; Se você não fizer isso, a guia **relatório** não será exibida na interface do usuário do console de operações. Observe que depois de reiniciar o console de operações pela primeira vez, pode demorar vários minutos antes de todos os relatórios de monitoramento serem exibidos na guia **relatório** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

