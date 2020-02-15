---
title: 'Lync Server 2013: usando o Microsoft SQL Server 2008 R2 como banco de dados do System Center Operations Manager'
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
ms.openlocfilehash: 6ad7854043eb85db7b5d260d57beed26746160f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>Usando o Microsoft SQL Server 2008 R2 como seu banco de dados do System Center Operations Manager para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-29_

Para usar o SQL Server 2008 R2 como banco de dados back-end, conclua as etapas detalhadas neste tópico.

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>Configurando o SQL Server 2008 R2 e o SQL Server Reporting Services

Antes de começar a instalação do System Center Operations Manager, você deve fazer duas alterações no SQL Server 2008 R2 e na configuração do SQL Server Reporting Services. (Essas alterações só serão necessárias se você estiver usando o SQL Server 2008 R2 como seu banco de dados do Operations Manager.) Primeiro, faça o seguinte no computador que hospedará o banco de dados do Operations Manager:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa de diálogo **executar** , digite **C:\\\\arquivos de programa Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting Services\\ReportServer** e pressione Enter.

3.  Na pasta **ReportServer**, abra o arquivo **rsreportserver.config** no Bloco de Notas ou em qualquer outro editor de texto.

4.  Próximo ao início do arquivo, você verá uma série de nós "Add Key". Encontre a entrada que começa ** \<a adicionar Key = "SecureConnectionLevel"** e defina o valor como **0**:
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  Salve o arquivo **rsreportserver.config** e feche o editor de texto.

Depois de atualizar o arquivo de configuração do Report Server, você deve atribuir o certificado correto ao SQL Server Reporting Services. Para isso:

1.  Clique em **Iniciar**, **em todos os programas**, em **Microsoft SQL Server 2008 R2**, em **ferramentas de configuração**e em Gerenciador de configuração do **Reporting Services**.

2.  Na caixa de diálogo **Conexão de Configuração do Reporting Services**, certifique-se de que o nome do seu servidor aparece na caixa **Nome do Servidor**. Selecione a instância do SQL Server que hospedará o banco de dados do Operations Manager (por exemplo, **ARCHINST**) na lista suspensa **instância do servidor de relatório** e clique em **conectar**.

3.  No Gerenciador de Configuração do Reporting Services, clique em **URL do Serviço Web**.

4.  Na página **URL do Serviço Web**, selecione o certificado a ser usado para o seu Reporting Services na lista suspensa **Certificado SSL** e clique em **Aplicar**. Depois de alguns segundos, você verá duas URLs listadas sob **URLs do Serviço Web do Servidor de Relatórios**.

5.  Clique em ambas para verificar se pode acessar o SQL Server Reporting Services.

6.  Feche o Gerenciador de Configuração do Reporting Services.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>Criando um banco de dados do System Center Operations Manager para uso com o SQL Server 2008 R2

Se você quiser configurar o System Center Operations Manager para usar um banco de dados do SQL Server 2008 R2, será necessário criar manualmente o banco de dados do Operations Manager no computador que executa o SQL Server 2008 R2. (Novamente, essas etapas não são necessárias se você estiver usando o SQL Server 2005 ou o SQL Server 2008 como seu banco de dados de back-end.)

Para criar um banco de dados do Operations Manager manualmente, faça o seguinte:

1.  Na mídia de instalação do System Center Operations Manager 2007 R2, na\\pasta SupportTools AMD64, clique duas vezes em **DBCreateWizard. exe**.

2.  No Assistente para Configuração do Banco de Dados, na página **Benvindo ao Assistente para Configuração do Banco de Dados**, clique em **Avançar**.

3.  Na página **Informações do Banco de Dados**, deixe todas as configurações como estão e clique em **Avançar**

4.  Na página **configuração do grupo de gerenciamento** , digite um nome para o grupo de gerenciamento (por exemplo, **monitoramento do Lync Server**) na caixa **nome do grupo de gerenciamento** e clique em **Avançar**.

5.  Na página **Relatórios de Erros do Operations Manager**, clique em **Avançar**.

6.  Na página **Resumo**, clique em **Concluir**.

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>Criando um data warehouse do System Center Operations Manager para uso com o SQL Server 2008 R2

O Microsoft Lync Server 2013 acompanha três novos relatórios do System Center Operations Manager:

  - **Relatório de disponibilidade de cenário de ponta a ponta**   este relatório detalha a disponibilidade/tempo de atividade para os principais serviços do Lync Server, como registro ou presença.

  - **Relatório de capacidade**   usando informações de contador de desempenho, este relatório mostra tendências para componentes do sistema, como disponibilidade de memória e uso do processador.

  - **Relatório de componente**   este relatório lista os principais geradores de alerta agrupados pelo componente do Lync Server.

Para usar esses novos relatórios, você deve instalar um data warehouse do System Center Operations Manager. (Um data warehouse fornece um armazenamento de dados de longo prazo de operações.) Para usar um data warehouse com o SQL Server 2008 R2, você deve executar as seguintes etapas no computador que hospeda o banco de dados do SQL Server:

1.  Na mídia de instalação do System Center Operations Manager, na\\pasta\\setup SupportTools AMD64, clique duas vezes em **DBCreateWizard. exe**.

2.  No Assistente para Configuração do Banco de Dados, na página **Benvindo ao Assistente para Configuração do Banco de Dados**, clique em **Avançar**.

3.  Na página **Informações do Banco de Dados**, selecione **Banco de Dados Data Warehouse do Operations Manager** na lista suspensa **Tipo de Banco de Dados** e clique em **Avançar**.

4.  Na página **Resumo**, clique em **Concluir**.

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>Instalando o console do System Center Operations Manager

O console do Operations Manager é a principal ferramenta usada para gerenciar o System Center Operations Manager. Antes de instalar o console do Operations Manager, verifique se você instalou uma versão com suporte do SQL Server, juntamente com o SQL Server Reporting Service. Também é recomendado executar o Gerenciador de Configuração do SQL Server Reporting Services para verificar se o Serviço de Relatórios foi instalado e configurado corretamente.

Para instalar o console do System Center Operations Manager:

1.  Na mídia de instalação do System Center Operations Manager, clique duas vezes em **SetupOM. exe**.

2.  Na instalação do System Center Operations Manager 2007 R2, clique em **verificar pré-requisitos**.

3.  No Visualizador de pré-requisitos do System Center Operations Manager, selecione os componentes do System Center que serão instalados: (**servidor**; **Console**; e **PowerShell**) e clique em **verificar**. Verifique se nenhum problema de bloqueio foi identificado e clique em **Fechar**. Se um problema de bloqueio foi identificado, corrija-o e clique em **Verificar** para executar novamente o teste de pré-requisitos.

4.  Na instalação do System Center Operations Manager, clique em **instalar o Operations Manager**.

5.  No assistente de instalação do System Center Operations Manager, na página **Bem-vindo ao assistente de instalação do System Center Operations Manager** , clique em **Avançar**.

6.  Na página **Contrato de Licença do Usuário Final**, selecione **Aceito os termos do contrato de licença** e clique em **Avançar**.

7.  Na página **Registro do Produto**, digite seu nome na caixa **Nome do Usuário** e o nome da sua organização na caixa **Organização**. Digite sua chave do produto do System Center Operations Manager na caixa **Insira a chave do CD de 25 dígitos** e clique em **Avançar**.

8.  Na página **Instalação Personalizada**, selecione as opções do System Center a serem instaladas e clique em **Avançar**. Você deve selecionar **Servidor de Gerenciamento**, **Interfaces de Usuário** e **Console Web**. A opção **Banco de Dados** não deve ser selecionada e não deve ser instalada.

9.  Na página **instância do servidor de banco de dados SC** , verifique se o nome do computador onde os bancos de dados do Operations Manager estão instalados aparece na caixa **servidor de banco de dados do System Center** . Clique em **Avançar**.

10. Na página **Conta de Ação do Servidor de Gerenciamento**, selecione **Conta de Domínio ou do Computador Local** e insira os valores adequados nas caixas **Conta de Usuário**, **Senha** e **Domínio ou computador local**. Clique em **Avançar**.

11. Na página **SDK e Conta de Serviço de Configuração**, selecione **Conta de Domínio ou do Computador Local** e insira os valores adequados nas caixas **Conta de Usuário**, **Senha** e **Domínio ou computador local**. Clique em **Avançar**.

12. Na página **Relatórios de Erros do Operations Manager**, clique em **Avançar**.

13. Na página **Programa de Aperfeiçoamento da Experiência do Usuário**, clique em **Avançar**.

14. Na página **Pronto para Instalar o Programa**, clique em **Instalar**.

15. Na página **Concluindo a Instalação do System Center Operations Manager**, desmarque as opções **Chave de Criptografia de Backup** e **Iniciar o console** e clique em **Concluir**.

16. Na instalação do System Center Operations Manager, clique em **sair**.

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>Como instalar o System Center Reporting Services

Após instalar e configurar o console do System Center Operations Manager, você deve instalar o System Center Reporting Services. Se você estiver usando o SQL Server 2008 R2 como o banco de dados back-end do Operations Manager, isso significa que você deve primeiro fazer uma alteração temporária no grupo de segurança associado ao SQL Server Reporting Services. Se você estiver usando o SQL Server 2008 R2, deverá fazer o seguinte:

1.  Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciador de Servidores**.

2.  No Gerenciador de Servidores, expanda **Configuração**, **Usuários e Grupos Locais** e clique em **Grupos**.

3.  Localize o grupo a seguir, em que ATL-SC-001 representa o nome do seu computador e ARCHINST representa a instância do SQL Server para o banco de dados do System Center: **SQLServerReportServerUser $ ATL\_-SC-001 $ MSRS10 50. ARCHINST**.

4.  Clique com o botão direito no grupo e clique em **Renomear**. Renomeie o grupo excluindo ** \_50** do nome do grupo. Por exemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

5.  Feche o Gerenciador de Servidores.

Neste ponto, você está pronto para instalar o System Center Reporting Services. Para isso:

1.  Na mídia de instalação do System Center Operations Manager 2007 R2, clique duas vezes em **SetupOM. exe**.

2.  Na instalação do System Center Operations Manager 2007 R2, clique em **instalar o Operations Manager Reporting**.

3.  No assistente de instalação de relatórios do System Center Operations Manager 2007 R2, na página **Bem-vindo à instalação de relatórios do Operations Manager** , clique em **Avançar**.

4.  Na página **Contrato de Licença do Usuário Final**, selecione **Aceito os termos do contrato de licença** e clique em **Avançar**.

5.  Na página **Registro do Produto**, certifique-se de que seu nome e o nome da sua organização aparecem nas caixas **Nome do Usuário** e **Organização** e clique em **Avançar**.

6.  Na página **Instalação Personalizada**, clique em **Servidor de Relatórios** e selecione **Este componente e todos os componentes dependentes serão instalados no disco rígido local**. Clique em **Data Warehouse** e selecione **Este componente não estará disponível** e clique em **Avançar**.

7.  Na página **Conectar ao servidor de gerenciamento raiz**, digite o nome do servidor de gerenciamento raiz do seu Operations Manager na caixa **Servidor de Gerenciamento Raiz** e clique em **Avançar**.

8.  Na página **Conectar ao Data Warehouse do Operations Manager**, digite a instância do SQL Server em que seu data warehouse está localizado na caixa **Instância do SQL Server** (se seu data warehouse estiver localizado na instância padrão, digite simplesmente o nome do servidor; por exemplo: atl-sql-001). Verifique se o nome do banco de dados **OperationsManagerDW** aparece na caixa **Nome** e se a porta **1433** aparece na caixa **Porta do SQL Server**. Clique em **Avançar**.

9.  Na página **Instância dos Relatórios do SQL Server**, selecione o servidor de relatórios do SQL Server na lista suspensa **Insira o Servidor do SQL Server Reporting Services** e clique em **Avançar**.

10. Na página **Conta de Gravação do Data Warehouse**, insira o nome e senha do usuário a quem serão inicialmente atribuídas permissões de gravação no data warehouse nas caixas **Conta de Usuário** e **Senha**. Selecione o domínio do usuário na lista suspensa **Domínio** e clique em **Avançar**.

11. Na página **Conta do Leitor de Dados**, insira o nome e senha da conta de usuário a ser usada quando o SQL Reporting Services consultar o data warehouse nas caixas **Conta de Usuário** e **Senha**. Selecione o domínio da conta na lista suspensa **Domínio** e clique em **Avançar**.

12. Na página **Relatórios de Dados Operacionais**, clique em **Avançar**.

13. Na página **Microsoft Update**, clique em **Avançar**.

14. Na página **Pronto para instalar o programa**, clique em **Instalar**.

15. Na página **Concluindo o Assistente de Instalação dos Componentes de Relatórios do Operations Manager**, clique em **Concluir**.

16. Na instalação do System Center Operations Manager 2007 R2, clique em **sair**.

Após a instalação do System Center Reporting, use o procedimento a seguir para redefinir o nome do grupo de segurança associado ao relatório do SQL Server. Novamente, esse procedimento só será necessário se você estiver usando o SQL Server:

1.  Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciador de Servidores**.

2.  No Gerenciador de Servidores, expanda **Configuração**, **Usuários e Grupos Locais** e clique em **Grupos**.

3.  Localize o grupo a seguir, em que ATL-SC-001 representa o nome do seu computador e ARCHINST representa a instância do SQL Server para os bancos de dados de arquivamento e monitoramento: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.

4.  Clique com o botão direito no grupo e clique em **Renomear**. Renomeie o grupo adicionando ** \_50** ao final do nome do grupo, imediatamente antes do nome da instância do SQL Server. Por exemplo: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.

5.  Feche o Gerenciador de Servidores.

Se o Console de Operações do System Center estiver aberto, será necessário fechar o aplicativo e reiniciá-lo; se você não o fizer, a guia **Relatórios** não aparecerá na interface do usuário do Console de Operações. Observe que depois de reiniciar o Console de Operações pela primeira vez, pode demorar vários minutos até que todos os Relatórios de Monitoramento apareçam na guia **Relatórios**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

