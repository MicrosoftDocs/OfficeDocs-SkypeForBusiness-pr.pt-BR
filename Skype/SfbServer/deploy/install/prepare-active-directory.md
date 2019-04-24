---
title: Preparar o Active Directory para Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Resumo: Saiba como preparar o domínio do Active Directory para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: de5de35377e526844a7badeb9897fe29b4b15db4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210617"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Preparar o Active Directory para Skype para Business Server
 
**Resumo:** Saiba como preparar o domínio do Active Directory para uma instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server a partir do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype para Business Server trabalha junto com o Active Directory. Você deve preparar o domínio do Active Directory para funcionar com Skype para Business Server. Esse processo é realizado no Assistente de implantação e é feito apenas uma vez para o domínio. Isso acontece porque o processo cria grupos e modifica o domínio, e isso só precisa ser feito uma vez. Você pode executar as etapas de 1 a 5 em qualquer ordem. Entretanto, deve executar as etapas 6, 7 e 8 na ordem certa, e após as etapas de 1 a 5, conforme descrito no diagrama. Preparar o Active Directory é a etapa 4 de 8. Para obter mais informações sobre o planejamento do Active Directory, consulte [requisitos de ambiente para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagrama de visão geral](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar o Active Directory

Skype para Business Server está estreitamente integrado com os serviços de domínio Active Directory (AD DS). Antes de Skype para Business Server pode ser instalado pela primeira vez, o Active Directory devem ser preparado. A seção do Assistente para implantação intitulado **Preparar o Active Directory** prepara o ambiente do Active Directory para uso com Skype para Business Server.
  
> [!NOTE]
> Skype para Business Server usa (AD DS) para controlar e se comunicar com todos os servidores em uma topologia. Cada servidor deve ser parte do domínio para que Skype para Business Server pode funcionar corretamente. 
  
> [!IMPORTANT]
> O procedimento Preparar o Active Directory deve ser executado apenas uma vez para cada domínio na implantação. 
  
Veja as etapas do vídeo para **Preparar o Active Directory**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Procedimento Preparar o Active Directory do Assistente de implantação

1. Faça logon como um usuário com credenciais de Administrador de Esquema para o domínio do Active Directory.
    
2. Abra o Skype para o Assistente de implantação de servidor de negócios.
    
    > [!TIP]
    > Se desejar examinar os arquivos de log são criados pelo Skype para o Assistente de implantação do Business Server, você pode encontrá-los no computador onde o Assistente de implantação foi executado, no diretório de usuários do usuário AD DS que executou a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio, Contoso, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Clique no link **Preparar o Active Directory**.
    
4. **Etapa 1: Preparar o esquema**
    
    a. Examine as informações de pré-requisitos para a Etapa 1, que podem ser acessadas clicando na lista suspensa embaixo do título da Etapa 1.
    
    b. Clique em **Executar** na Etapa 1 para inicializar o assistente Preparar esquema.
    
    c. Observe que o procedimento será executado apenas uma vez para cada implantação e, em seguida, clique em **Avançar**.
    
    d. Assim que o esquema for preparado, você poderá exibir o log clicando em **Exibir log**. 
    
    f. Clique em **Concluir** para fechar o assistente Preparar esquema e volte para as etapas de Preparar o Active Directory.
    
5. **Etapa 2: Verificar a replicação da partição do esquema**
    
    a. Faça logon no controlador de domínio.
    
    b. Abra **Editar ADSI** a partir do menu suspenso **Ferramentas** em **Gerenciador do Servidor**.
    
    c. No menu **Ação**, clique em **Conectar-se a**.
    
    d. Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
    f. No contêiner de esquema, procure por **CN=ms-RTC-SIP-SchemaVersion**. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** for 3, o esquema terá sido atualizado e replicado com êxito. Se esse objeto não existir ou se os valores dos atributos **rangeUpper** e **rangeLower** não seguirem a especificação, o esquema não terá sido modificado ou replicado.
    
6. **Etapa 3: Preparar a floresta atual**
    
    a. Examine as informações de pré-requisitos para a Etapa 3, que podem ser acessadas clicando na lista suspensa embaixo do título da Etapa 3.
    
    b. Clique em **Executar** na Etapa 3 para inicializar o assistente Preparar a floresta atual.
    
    c. Observe que o procedimento será executado apenas uma vez por implantação e, em seguida, clique em **Avançar**.
    
    d. Especifique o domínio no qual os grupos universais serão criados. Se o servidor fizer parte do domínio, você poderá escolher **Domínio local** e clicar em **Avançar**.
    
    f. Assim que a floresta for preparada, você poderá exibir o log clicando em **Exibir log**. 
    
    f. Clique em **Concluir** para fechar o assistente Preparar a floresta atual e volte para as etapas de Preparar o Active Directory.
    
    g. Clique em **Skype do Shell de gerenciamento do servidor de negócios** da página de **aplicativos** para o início do PowerShell.
    
    h. Digite o comando Get-CsAdForest e pressione **Enter**.
    
    Eu. Se o resultado for **LC_FORESTSETTINGS_STATE_READY**, a floresta com êxito foi preparada, conforme mostrado na figura.
    
     ![Verificar a replicação da floresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Etapa 4: Verificar a replicação do catálogo global**
    
    a. Em um controlador de domínio (preferencialmente em um local remoto de outros controladores de domínio), na floresta na qual a Preparação da floresta foi executada, abra **Usuários e Computadores do Active Directory**.
    
    b. Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio da sua floresta ou um domínio filho.
    
    c. Clique no contêiner **Usuários** no painel lateral esquerdo e procure o grupo Universal **CsAdministrator** no painel lateral direito. Se CsAdministrator (entre outros grupos Universais novos que começam com Cs) estiver presente, a replicação do Active Directory terá sido bem-sucedida.
    
    d. Se os grupos ainda não estiverem presentes, você poderá forçar a replicação ou aguardar 15 minutos e atualizar o painel lateral direito. Quando os grupos estiverem presentes, a replicação será concluída.
    
8. **Etapa 5: Preparar o domínio atual**
    
    a. Examine as informações de pré-requisitos para a Etapa 5.
    
    b. Clique em **Executar** na Etapa 5 para inicializar o assistente Preparar o domínio atual.
    
    c. Observe que o procedimento será executado apenas uma vez para cada domínio na implantação e, em seguida, clique em **Avançar**.
    
    d. Assim que o domínio for preparado, você poderá exibir o log clicando em **Exibir log**. 
    
    f. Clique em **Concluir** para fechar o assistente Preparar o domínio atual e volte para as etapas de Preparar o Active Directory.
    
    Estas etapas devem ser concluídas em cada domínio onde Skype para objetos Business Server forem encontrados, caso contrário, services pode não iniciar. Isso inclui qualquer tipo de objeto do Active Directory, como usuários, objetos de contato, grupos administrativos ou qualquer outro tipo de objeto. Você pode usar Set-CsUserReplicatorConfiguration - ADDomainNamingContextList para adicionar apenas aos domínios com Skype para objetos de servidor de negócios, se necessário.
    
9. **Etapa 6: Verificar a replicação no domínio**
    
    a. Clique no **Skype do Shell de gerenciamento do servidor de negócios** da página de **aplicativos** para iniciar o PowerShell.
    
    b. Use o comando Get-CsAdDomain para verificar a replicação dentro do domínio.
    
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
  
    c. Se o resultado for **LC_DOMAINSETTINGS_STATE_READY**, o domínio foi replicada com êxito.
    
10. **Etapa 7: Adicionar usuários para fornecer acesso administrativo para o Painel de Controle do Skype for Business Server**
    
    a. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
    b. Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique no contêiner **Usuários**, clique com o botão direito do mouse em CSAdministrator e escolha **Propriedades**.
    
    c. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
    d. Na guia **Membros**, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
    f. Na guia **Membros**, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
    > [!CAUTION]
    > O Skype para painel de controle do Business Server é uma ferramenta de controle de acesso baseado em função. A associação ao grupo CsAdministrator oferece um usuário que você está usando o Skype para controle total do painel de controle do servidor de negócios para todas as funções de configuração disponíveis. Há outras funções disponíveis que foram projetadas para funções específicas. Para obter detalhes sobre as funções disponíveis, consulte [requisitos de ambiente para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Observe que os usuários não precisam estar habilitado para Skype para Business Server para se tornar membros dos grupos de gerenciamento. 
  
    > [!CAUTION]
    > Para ajudar a manter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário executa no gerenciamento do Skype para implantação de servidor de negócios. 
  
11. Faça logoff e logon novamente no Windows para que o token de segurança é atualizada com o novo Skype para o grupo de segurança do servidor de negócios e reabra o Assistente de implantação.
    
12. Verifique se há uma marca de seleção verde perto de **Preparar o Active Directory** para confirmar o sucesso da implantação, conforme mostrado na imagem.
    
     ![Prepare o Active Directory foram concluídas.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Confira também
 
[Active Directory Domain Services for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
