---
title: Preparar o Active Directory para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Resumo: saiba como preparar seu domínio do Active Directory para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018172"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Preparar o Active Directory para o Skype for Business Server
 
**Resumo:** Saiba como preparar seu domínio do Active Directory para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no [centro de avaliação da Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
O Skype for Business Server funciona em conjunto com o Active Directory. Você deve preparar o domínio do Active Directory para trabalhar com o Skype for Business Server. Esse processo é realizado no assistente de implantação e só é executado uma vez para o domínio. Isso ocorre porque o processo cria grupos e modifica o domínio, e você precisa fazer isso apenas uma vez. Você pode executar as etapas 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 em ordem e depois das etapas de 1 a 5, conforme descrito no diagrama. A preparação do Active Directory é a etapa 4 de 8. Para obter mais informações sobre o planejamento do Active Directory, consulte [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagrama de visão geral](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar o Active Directory

O Skype for Business Server está totalmente integrado aos serviços de domínio do Active Directory (AD DS). Antes que o Skype for Business Server possa ser instalado pela primeira vez, o Active Directory deve ser preparado. A seção do assistente de implantação intitulado **preparar o Active Directory** prepara o ambiente do Active Directory para uso com o Skype for Business Server.
  
> [!NOTE]
> O Skype for Business Server usa (AD DS) para rastrear e se comunicar com todos os servidores em uma topologia. A maioria desses servidores deve ser associada ao domínio para que o Skype for Business Server possa funcionar corretamente. Tenha em mente que servidores como borda e proxy reverso não devem ser associados ao domínio.
  
> [!IMPORTANT]
> O procedimento preparar o Active Directory deve ser executado apenas uma vez para cada domínio na implantação. 
  
Assista as etapas de vídeo para **preparar o Active Directory**:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparar o Active Directory do assistente de implantação

1. Faça logon como um usuário com credenciais de administradores de esquema para o domínio do Active Directory.
    
2. Abra o assistente de implantação do Skype for Business Server.
    
    > [!TIP]
    > Se você deseja revisar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você pode encontrá-los no computador onde o assistente de implantação foi executado, no diretório Users do usuário do AD DS que executou a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio, contoso. local, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Clique no link **preparar o Active Directory** .
    
4. **Etapa 1: preparar o esquema**
    
    a. Revise as informações de pré-requisitos para a etapa 1, que podem ser acessadas clicando na lista suspensa sob o título da etapa 1.
    
    b. Clique em **executar** na etapa 1 para iniciar o assistente para preparar esquema.
    
    c. Observe que o procedimento deve ser executado apenas uma vez para cada implantação e, em seguida, clique em **Avançar**.
    
    d. Depois que o esquema tiver sido preparado, você poderá exibir o log clicando em **Exibir log**. 
    
    e. Clique em **concluir** para fechar o assistente para preparar esquema e retorne às etapas preparar o Active Directory.
    
5. **Etapa 2: verificar a replicação da partição de esquema**
    
    a. Faça logon no controlador de domínio do domínio.
    
    b. Abra **ADSI Edit** no menu suspenso **ferramentas** no **Gerenciador do servidor**.
    
    c. No menu **Ação**, clique em **Conectar-se a**.
    
    d. Na caixa de diálogo **Configurações de Conexão** em **Selecione um Contexto de Nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
    e. No contêiner de esquema, procure **CN = ms-RTC-SIP-SchemaVersion**. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **RangeLower** for 3, o esquema foi atualizado e replicado com êxito. Se esse objeto não existir ou se os valores dos atributos **rangeUpper** e **RangeLower** não forem especificados, o esquema não foi modificado ou não foi replicado.
    
6. **Etapa 3: preparar a floresta atual**
    
    a. Revise as informações de pré-requisitos para a etapa 3, que podem ser acessadas clicando na lista suspensa sob o título da etapa 3.
    
    b. Clique em **executar** na etapa 3 para iniciar o assistente para preparar a floresta atual.
    
    c. Observe que o procedimento deve ser executado apenas uma vez por implantação e, em seguida, clique em **Avançar**.
    
    d. Especifique o domínio no qual os grupos universais serão criados. Se o servidor fizer parte do domínio, você poderá escolher **domínio local**e clicar em **Avançar**.
    
    e. Depois que a floresta tiver sido preparada, você poderá exibir o log clicando em **Exibir log**. 
    
    f. Clique em **concluir** para fechar o assistente preparar a floresta atual e retorne às etapas preparar o Active Directory.
    
    g. Clique em **Shell de gerenciamento do Skype for Business Server** na página **aplicativos** para iniciar o PowerShell.
    
    0. Digite o comando Get-CsAdForest e pressione **Enter**.
    
    crio. Se o resultado for **LC_FORESTSETTINGS_STATE_READY**, a floresta foi preparada com êxito, conforme mostrado na figura.
    
     ![Verifique a replicação da floresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Etapa 4: verificar a replicação do catálogo global**
    
    a. Em um controlador de domínio (preferencialmente em um site remoto de outros controladores de domínio), na floresta na qual a Preparação da Floresta foi executada, abra **Usuários e Computadores do Active Directory**.
    
    b. Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio de sua floresta ou domínio filho.
    
    c. Clique no contêiner **usuários** no painel esquerdo e procure o grupo universal **CsAdministrator** no painel direito. Se o CsAdministrator (entre outros novos grupos universais que começam com o CS) estiver presente, a replicação do Active Directory terá sido bem-sucedida.
    
    d. Se os grupos ainda não estiverem presentes, você poderá forçar a replicação ou aguardar 15 minutos e atualizar o painel do lado direito. A replicação está completa quando os grupos estiverem presentes.
    
8. **Etapa 5: preparar o domínio atual**
    
    a. Revise as informações de pré-requisitos para a etapa 5.
    
    b. Clique em **executar** na etapa 5 para iniciar o assistente para preparar domínio atual.
    
    c. Observe que o procedimento deve ser executado apenas uma vez para cada domínio na implantação e, em seguida, clique em **Avançar**.
    
    d. Depois que o domínio tiver sido preparado, você poderá exibir o log clicando em **Exibir log**. 
    
    e. Clique em **concluir** para fechar o assistente preparar domínio atual e retorne às etapas preparar o Active Directory.
    
    Essas etapas devem ser concluídas em todos os domínios em que os objetos do Skype for Business Server sejam encontrados; caso contrário, os serviços poderão não ser iniciados. Isso inclui qualquer tipo de objeto do Active Directory, como usuários, objetos de contato, grupos administrativos ou qualquer outro tipo de objeto. Você pode usar set-CsUserReplicatorConfiguration-ADDomainNamingContextList para adicionar apenas os domínios com objetos do Skype for Business Server, se necessário.
    
9. **Etapa 6: verificar a replicação no domínio**
    
    a. Clique no **Shell de gerenciamento do Skype for Business Server** na página **aplicativos** para iniciar o PowerShell.
    
    b. Use o comando Get-CsAdDomain para verificar a replicação no domínio.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Se você não especificar o parâmetro Domínio, o valor é configurado para o domínio local. 
  
    Exemplo de execução do comando para o domínio contoso. local:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Usando o parâmetro GlobalSettingsDomainController, você pode indicar onde as configurações globais são armazenadas. Se suas configurações são armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tinham a configuração global migrada para o contêiner de configuração), você define um controlador de domínio na raiz da sua floresta do AD DS. Se as configurações globais estiverem no contêiner Configuração (o que é típico nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você define qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio no Active Directory. 
  
    c. Se o resultado for **LC_DOMAINSETTINGS_STATE_READY**, o domínio foi replicado com êxito.
    
10. **Etapa 7: adicionar usuários para fornecer acesso administrativo ao painel de controle do Skype for Business Server**
    
    a. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
    b. Abra **usuários e computadores do Active Directory**, expanda seu domínio, clique no contêiner **usuários** , clique com o botão direito do mouse em CSAdministrator e escolha **Propriedades**.
    
    c. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
    d. Na guia **Membros**, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
    e. Na guia **Membros** , confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
    > [!CAUTION]
    > O painel de controle do Skype for Business Server é uma ferramenta de controle de acesso baseada em função. A associação ao grupo CsAdministrator fornece um usuário que está usando o controle total do painel de controle do Skype for Business Server para todas as funções de configuração disponíveis. Há outras funções disponíveis que foram projetadas para funções específicas. Para obter detalhes sobre as funções disponíveis, consulte [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Observe que os usuários não precisam estar habilitados para o Skype for Business Server a fim de se tornar membros dos grupos de gerenciamento. 
  
    > [!CAUTION]
    > Para ajudar a manter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário executa no gerenciamento da implantação do Skype for Business Server. 
  
11. Faça logoff e, em seguida, faça logon novamente no Windows para que o token de segurança seja atualizado com o novo grupo de segurança do Skype for Business Server e reabra o assistente de implantação.
    
12. Verifique se você vê uma marca de verificação verde ao lado de **preparar o Active Directory** para confirmar o sucesso, conforme mostrado na figura.
    
     ![Preparar o Active Directory concluído.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Confira também
 
[Serviços de domínio do Active Directory para o Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
