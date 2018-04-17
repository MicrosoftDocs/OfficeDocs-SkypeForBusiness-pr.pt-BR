---
title: Preparar o Active Directory para Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Summary: Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a1344bab451bd9c4b46a0147bd2ffb1190dbe900
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Preparar o Active Directory para Skype for Business Server 2015
 
**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server works closely with Active Directory. You must prepare the Active Directory domain to work with Skype for Business Server. Esse processo é realizado no Assistente de implantação e é feito apenas uma vez para o domínio. Isso acontece porque o processo cria grupos e modifica o domínio, e isso só precisa ser feito uma vez. Você pode executar as etapas de 1 a 5 em qualquer ordem. Entretanto, deve executar as etapas 6, 7 e 8 na ordem certa, e após as etapas de 1 a 5, conforme descrito no diagrama. Preparar o Active Directory é a etapa 4 de 8. For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![diagrama de visão geral](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar o Active Directory

Skype for Business Server 2015 is tightly integrated with Active Directory Domain Services (AD DS). Before Skype for Business Server 2015 can be installed for the first time, Active Directory must be prepared. The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server 2015 uses (AD DS) to track and communicate with all of the servers in a topology. Every server must be joined to the domain so that Skype for Business Server can work properly. 
  
> [!IMPORTANT]
> O procedimento Preparar o Active Directory deve ser executado apenas uma vez para cada domínio na implantação. 
  
Veja as etapas do vídeo para **Preparar o Active Directory**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/272c856b-b3e0-4324-9635-42720c48b75a?autoplay=false]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Procedimento Preparar o Active Directory do Assistente de implantação

1. Faça logon como um usuário com credenciais de Administrador de Esquema para o domínio do Active Directory.
    
2. Open Skype for Business Server Deployment Wizard.
    
    > [!TIP]
    > If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step. For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Clique no link **Preparar o Active Directory**.
    
4. **Step 1: Prepare schema**
    
    a. Examine as informações de pré-requisitos para a Etapa 1, que podem ser acessadas clicando na lista suspensa embaixo do título da Etapa 1.
    
    b. Clique em **Executar** na Etapa 1 para inicializar o assistente Preparar esquema.
    
    c. Observe que o procedimento será executado apenas uma vez para cada implantação e, em seguida, clique em **Avançar**.
    
    d. Assim que o esquema for preparado, você poderá exibir o log clicando em **Exibir log**. 
    
    e. Clique em **Concluir** para fechar o assistente Preparar esquema e volte para as etapas de Preparar o Active Directory.
    
5. **Step 2: Verify replication of schema partition**
    
    a. Faça logon no controlador de domínio.
    
    b. Abra **Editar ADSI** a partir do menu suspenso **Ferramentas** em **Gerenciador do Servidor**.
    
    c. No menu **Ação**, clique em **Conectar-se a**.
    
    d. Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
    e. No contêiner de esquema, procure por **CN=ms-RTC-SIP-SchemaVersion**. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** for 3, o esquema terá sido atualizado e replicado com êxito. Se esse objeto não existir ou se os valores dos atributos **rangeUpper** e **rangeLower** não seguirem a especificação, o esquema não terá sido modificado ou replicado.
    
6. **Step 3: Prepare current forest**
    
    a. Examine as informações de pré-requisitos para a Etapa 3, que podem ser acessadas clicando na lista suspensa embaixo do título da Etapa 3.
    
    b. Clique em **Executar** na Etapa 3 para inicializar o assistente Preparar a floresta atual.
    
    c. Observe que o procedimento será executado apenas uma vez por implantação e, em seguida, clique em **Avançar**.
    
    d. Especifique o domínio no qual os grupos universais serão criados. Se o servidor fizer parte do domínio, você poderá escolher **Domínio local** e clicar em **Avançar**.
    
    e. Assim que a floresta for preparada, você poderá exibir o log clicando em **Exibir log**. 
    
    f. Clique em **Concluir** para fechar o assistente Preparar a floresta atual e volte para as etapas de Preparar o Active Directory.
    
    g. Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    h. Type the command Get-CsAdForest, and press **Enter**.
    
    i. If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.
    
     ![Verificar replicação de floresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Step 4: Verify replication of the global catalog**
    
    a. Em um controlador de domínio (preferencialmente em um local remoto de outros controladores de domínio), na floresta na qual a Preparação da floresta foi executada, abra **Usuários e Computadores do Active Directory**.
    
    b. Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio da sua floresta ou um domínio filho.
    
    c. Clique no contêiner **Usuários** no painel lateral esquerdo e procure o grupo Universal **CsAdministrator** no painel lateral direito. Se CsAdministrator (entre outros grupos Universais novos que começam com Cs) estiver presente, a replicação do Active Directory terá sido bem-sucedida.
    
    d. Se os grupos ainda não estiverem presentes, você poderá forçar a replicação ou aguardar 15 minutos e atualizar o painel lateral direito. Quando os grupos estiverem presentes, a replicação será concluída.
    
8. **Step 5: Prepare the current domain**
    
    a. Examine as informações de pré-requisitos para a Etapa 5.
    
    b. Clique em **Executar** na Etapa 5 para inicializar o assistente Preparar o domínio atual.
    
    c. Observe que o procedimento será executado apenas uma vez para cada domínio na implantação e, em seguida, clique em **Avançar**.
    
    d. Assim que o domínio for preparado, você poderá exibir o log clicando em **Exibir log**. 
    
    e. Clique em **Concluir** para fechar o assistente Preparar o domínio atual e volte para as etapas de Preparar o Active Directory.
    
    These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start. Isso inclui qualquer tipo de objeto do Active Directory, como usuários, objetos de contato, grupos administrativos ou qualquer outro tipo de objeto. You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.
    
9. **Step 6: Verify replication in the domain**
    
    a. Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    b. Use the command Get-CsAdDomain to verify replication within the domain.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > Se você não especificar o parâmetro Domínio, o valor será definido como o domínio local. 
  
    Exemplo de execução de comando para o domínio contoso.local:
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > Ao usar o parâmetro GlobalSettingsDomainController, você pode indicar onde as configurações globais estão armazenadas. Se suas configurações estiverem armazenadas no contêiner Sistema (o que é normal em implantações de atualização que não tiveram a configuração global migrada para o contêiner Configuração), defina um controlador de domínio na raiz de sua floresta AD DS. Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory. 
  
    c. If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.
    
10. **Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**
    
    a. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
    b. Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique no contêiner **Usuários**, clique com o botão direito do mouse em CSAdministrator e escolha **Propriedades**.
    
    c. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
    d. Na guia **Membros**, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
    e. Na guia **Membros**, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
    > [!CAUTION]
    > The Skype for Business Server Control Panel is a role-based access control tool. Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available. Há outras funções disponíveis que foram projetadas para funções específicas. For details on the roles available, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups. 
  
    > [!CAUTION]
    > To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment. 
  
11. Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.
    
12. Verifique se há uma marca de seleção verde perto de **Preparar o Active Directory** para confirmar o sucesso da implantação, conforme mostrado na imagem.
    
     ![Preparação do Active Directory Concluída.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

