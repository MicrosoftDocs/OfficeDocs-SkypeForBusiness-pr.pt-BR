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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Resumo: saiba como preparar seu domínio do Active Directory para uma instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: a7b9a22042cecae76a5a5390b0778119363043b5
ms.sourcegitcommit: a6e051c5c5c100dbf2ff3ca8fc7babc4415babf3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2020
ms.locfileid: "41554048"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Preparar o Active Directory para o Skype for Business Server
 
**Resumo:** Saiba como preparar seu domínio do Active Directory para uma instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no [centro de avaliação da Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
O Skype for Business Server funciona em conjunto com o Active Directory. Você deve preparar o domínio do Active Directory para funcionar com o Skype for Business Server. Esse processo é realizado no Assistente de implantação e é feito apenas uma vez para o domínio. Isso acontece porque o processo cria grupos e modifica o domínio, e isso só precisa ser feito uma vez. Você pode executar as etapas de 1 a 5 em qualquer ordem. Entretanto, deve executar as etapas 6, 7 e 8 na ordem certa, e após as etapas de 1 a 5, conforme descrito no diagrama. Preparar o Active Directory é a etapa 4 de 8. Para obter mais informações sobre o planejamento do Active Directory, consulte [requisitos ambientais para](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) requisitos do servidor ou do servidor do Skype for Business [para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagrama de visão geral](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar o Active Directory

O Skype for Business Server está totalmente integrado aos serviços de domínio Active Directory (AD DS). Para que o Skype for Business Server possa ser instalado pela primeira vez, o Active Directory deve estar preparado. A seção do assistente de implantação intitulado **preparar o Active Directory** prepara o ambiente do Active Directory para uso com o Skype for Business Server.
  
> [!NOTE]
> O Skype for Business Server usa (AD DS) para acompanhar e se comunicar com todos os servidores em uma topologia. A maioria desses servidores deve ser associada ao domínio para que o Skype for Business Server possa funcionar corretamente. Lembre-se de que os servidores como o Edge e o proxy reverso não devem ser associados ao domínio.
  
> [!IMPORTANT]
> O procedimento Preparar o Active Directory deve ser executado apenas uma vez para cada domínio na implantação. 
  
Veja as etapas do vídeo para **Preparar o Active Directory**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Procedimento Preparar o Active Directory do Assistente de implantação

1. Faça logon como um usuário com credenciais de Administrador de Esquema para o domínio do Active Directory.
    
2. Abrir o assistente de implantação do Skype for Business Server.
    
    > [!TIP]
    > Se quiser analisar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você pode encontrá-los no computador em que o assistente de implantação foi executado, no diretório usuários do usuário do AD DS que executou a etapa. Por exemplo, se o usuário tiver feito logon como administrador de domínio no domínio, contoso. local, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Clique no link **Preparar o Active Directory**.
    
4. **Etapa 1: Preparar o esquema**
    
    a. Examine as informações de pré-requisitos para a Etapa 1, que podem ser acessadas clicando na lista suspensa embaixo do título da Etapa 1.
    
    b. Clique em **Executar** na Etapa 1 para inicializar o assistente Preparar esquema.
    
    c. Observe que o procedimento será executado apenas uma vez para cada implantação e, em seguida, clique em **Avançar**.
    
    d. Assim que o esquema for preparado, você poderá exibir o log clicando em **Exibir log**. 
    
    vocálico. Clique em **Concluir** para fechar o assistente Preparar esquema e volte para as etapas de Preparar o Active Directory.
    
5. **Etapa 2: Verificar a replicação da partição do esquema**
    
    a. Faça logon no controlador de domínio.
    
    b. Abra **Editar ADSI** a partir do menu suspenso **Ferramentas** em **Gerenciador do Servidor**.
    
    c. No menu **Ação**, clique em **Conectar-se a**.
    
    d. Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
    vocálico. No contêiner de esquema, procure por **CN=ms-RTC-SIP-SchemaVersion**. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** for 3, o esquema terá sido atualizado e replicado com êxito. Se esse objeto não existir ou se os valores dos atributos **rangeUpper** e **rangeLower** não seguirem a especificação, o esquema não terá sido modificado ou replicado.
    
6. **Etapa 3: Preparar a floresta atual**
    
    a. Examine as informações de pré-requisitos para a Etapa 3, que podem ser acessadas clicando na lista suspensa embaixo do título da Etapa 3.
    
    b. Clique em **Executar** na Etapa 3 para inicializar o assistente Preparar a floresta atual.
    
    c. Observe que o procedimento será executado apenas uma vez por implantação e, em seguida, clique em **Avançar**.
    
    d. Especifique o domínio no qual os grupos universais serão criados. Se o servidor fizer parte do domínio, você poderá escolher **Domínio local** e clicar em **Avançar**.
    
    vocálico. Assim que a floresta for preparada, você poderá exibir o log clicando em **Exibir log**. 
    
    letra. Clique em **Concluir** para fechar o assistente Preparar a floresta atual e volte para as etapas de Preparar o Active Directory.
    
    p. Clique em **Shell de gerenciamento do Skype for Business Server** na página **aplicativos** para iniciar o PowerShell.
    
    u. Digite o comando Get-CsAdForest e pressione **Enter**.
    
    Configur. Se o resultado for **LC_FORESTSETTINGS_STATE_READY**, a floresta foi preparada com êxito, conforme mostrado na figura.
    
     ![Verifique a replicação de floresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
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
    
    vocálico. Clique em **Concluir** para fechar o assistente Preparar o domínio atual e volte para as etapas de Preparar o Active Directory.
    
    Essas etapas devem ser concluídas em todos os domínios em que os objetos do Skype for Business Server forem encontrados; caso contrário, os serviços talvez não sejam iniciados. Isso inclui qualquer tipo de objeto do Active Directory, como usuários, objetos de contato, grupos administrativos ou qualquer outro tipo de objeto. Você pode usar set-CsUserReplicatorConfiguration-ADDomainNamingContextList para adicionar somente os domínios com objetos do Skype for Business Server, se necessário.
    
9. **Etapa 6: Verificar a replicação no domínio**
    
    a. Clique no **Shell de gerenciamento do Skype for Business Server** na página **aplicativos** para iniciar o PowerShell.
    
    b. Use o comando Get-CsAdDomain para verificar a replicação no domínio.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Se você não especificar o parâmetro Domínio, o valor será definido como o domínio local. 
  
    Exemplo de execução de comando para o domínio contoso.local:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Ao usar o parâmetro GlobalSettingsDomainController, você pode indicar onde as configurações globais estão armazenadas. Se suas configurações estiverem armazenadas no contêiner Sistema (o que é normal em implantações de atualização que não tiveram a configuração global migrada para o contêiner Configuração), defina um controlador de domínio na raiz de sua floresta AD DS. Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory. 
  
    c. Se o resultado for **LC_DOMAINSETTINGS_STATE_READY**, o domínio foi replicado com êxito.
    
10. **Etapa 7: Adicionar usuários para fornecer acesso administrativo para o Painel de Controle do Skype for Business Server**
    
    a. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
    b. Abra **Usuários e Computadores do Active Directory**, expanda seu domínio, clique no contêiner **Usuários**, clique com o botão direito do mouse em CSAdministrator e escolha **Propriedades**.
    
    c. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
    d. Na guia **Membros**, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
    vocálico. Na guia **Membros**, confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
    > [!CAUTION]
    > O painel de controle do Skype for Business Server é uma ferramenta de controle de acesso baseada em função. A associação no grupo CsAdministrator permite que um usuário que está usando o painel de controle do Skype for Business Server controle total para todas as funções de configuração disponíveis. Há outras funções disponíveis que foram projetadas para funções específicas. Para obter detalhes sobre as funções disponíveis, consulte [requisitos ambientais para](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) requisitos do servidor ou do Skype for Business Server [para o Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Observe que os usuários não precisam estar habilitados para o Skype for Business Server, a fim de se tornarem membros dos grupos de gerenciamento. 
  
    > [!CAUTION]
    > Para ajudar a reter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário executa no gerenciamento da implantação do Skype for Business Server. 
  
11. Faça logoff e, em seguida, conecte-se novamente no Windows para que o token de segurança seja atualizado com o novo grupo de segurança do Skype for Business Server e, em seguida, abra novamente o assistente de implantação.
    
12. Verifique se você vê uma marca de verificação verde ao lado de **preparar o Active Directory** para confirmar o êxito, conforme mostrado na figura.
    
     ![Preparação do Active Directory concluída.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Confira também
 
[Active Directory Domain Services for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
