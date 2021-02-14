---
title: Preparar o Active Directory para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: saiba como preparar seu domínio do Active Directory para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 6196855ffeaf33fbea11c47d56c620e3df9195ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801671"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Preparar o Active Directory para o Skype for Business Server
 
**Resumo:** Saiba como preparar seu domínio do Active Directory para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server do Centro [de Avaliação da Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
O Skype for Business Server funciona em estreita proximidade com o Active Directory. Você deve preparar o domínio do Active Directory para trabalhar com o Skype for Business Server. Esse processo é realizado no Assistente de Implantação e é feito apenas uma vez para o domínio. Isso porque o processo cria grupos e modifica o domínio, e você precisa fazer isso apenas uma vez. Você pode realizar as etapas 1 a 5 em qualquer ordem. No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. Preparar o Active Directory é a etapa 4 de 8. Para obter mais informações sobre o planejamento do Active Directory, consulte [Requisitos](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) de ambiente para Skype for Business Server ou requisitos de servidor para [o Skype for Business Server 2019.](../../../SfBServer2019/plan/system-requirements.md)
  
![diagrama de visão geral](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar o Active Directory

O Skype for Business Server está totalmente integrado aos Serviços de Domínio do Active Directory (AD DS). Para que o Skype for Business Server possa ser instalado pela primeira vez, o Active Directory deve ser preparado. A seção do Assistente de Implantação intitulada **Preparar o Active Directory** prepara o ambiente do Active Directory para uso com o Skype for Business Server.
  
> [!NOTE]
> O Skype for Business Server usa (AD DS) para rastrear e se comunicar com todos os servidores em uma topologia. A maioria desses servidores deve ser ingressada no domínio para que o Skype for Business Server possa funcionar corretamente. Tenha em mente que servidores como Borda e Proxy Reverso não devem ser ingressados no domínio.
  
> [!IMPORTANT]
> O procedimento Preparar o Active Directory deve ser executado apenas uma vez para cada domínio na implantação. 
  
Assista às etapas de vídeo para **Preparar o Active Directory:**
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparar o Active Directory do Assistente de Implantação

1. Faça logoff como um usuário com credenciais de Administradores de Esquema para o domínio do Active Directory.
    
2. Abra o Assistente de Implantação do Skype for Business Server.
    
    > [!TIP]
    > Se quiser revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, você poderá encontrá-los no computador no qual o Assistente de Implantação foi executado, no diretório Usuários do usuário do AD DS que fez a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio contoso.local, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Clique no link **Preparar o Active Directory.**
    
4. **Etapa 1: Preparar o esquema**
    
    a. Revise as informações de pré-requisitos da Etapa 1 que podem ser acessadas clicando na lista de lista abaixo do título da Etapa 1.
    
    b. Clique **em** Executar na Etapa 1 para iniciar o assistente Preparar Esquema.
    
    c. Observe que o procedimento deve ser executado apenas uma vez para cada implantação e clique em **Próximo.**
    
    d. Depois que o esquema tiver sido preparado, você poderá exibir o log clicando em **Exibir Log.** 
    
    e. Clique **em Concluir** para fechar o assistente Preparar Esquema e retorne às etapas preparar o Active Directory.
    
5. **Etapa 2: Verificar a replicação da partição do esquema**
    
    a. Faça logoff no controlador de domínio do domínio.
    
    b. Abra **o AdsI Edit** no menu suspenso Ferramentas no Gerenciador do **Servidor.** 
    
    c. No menu **Ação**, clique em **Conectar-se a**.
    
    d. Na caixa de diálogo **Configurações de Conexão** em **Selecione um Contexto de Nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.
    
    e. No contêiner de esquema, procure **CN=ms-RTC-SIP-SchemaVersion**. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** for 3, o esquema foi atualizado e replicado com êxito. Se esse objeto não existir ou os valores dos atributos **rangeUpper** e **rangeLower** não são como especificados, o esquema não foi modificado ou não foi replicado.
    
6. **Etapa 3: Preparar a floresta atual**
    
    a. Revise as informações de pré-requisitos da Etapa 3 que podem ser acessadas clicando na lista de lista abaixo do título da Etapa 3.
    
    b. Clique **em** Executar na Etapa 3 para iniciar o assistente Preparar Floresta Atual.
    
    c. Observe que o procedimento só deve ser executado uma vez por implantação e clique em **Próximo.**
    
    d. Especifique o domínio onde os grupos universais serão criados. Se o servidor faz parte do domínio, você pode escolher **o domínio local** e clicar em **Próximo.**
    
    e. Depois que a floresta tiver sido preparada, você poderá exibir o log clicando em **Exibir Log.** 
    
    f. Clique **em Concluir** para fechar o assistente Preparar Floresta Atual e retorne às etapas Preparar Active Directory.
    
    g. Clique **no Shell de Gerenciamento do Skype for Business Server** na página **Aplicativos** para iniciar o PowerShell.
    
    h. Digite o comando Get-CsAdForest e pressione **Enter**.
    
    i. Se o resultado for **LC_FORESTSETTINGS_STATE_READY**, a floresta foi preparada com êxito, conforme mostrado na figura.
    
     ![Verifique a replicação da floresta.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Etapa 4: Verificar a replicação do catálogo global**
    
    a. Em um controlador de domínio (preferencialmente em um site remoto de outros controladores de domínio), na floresta na qual a Preparação da Floresta foi executada, abra **Usuários e Computadores do Active Directory**.
    
    b. Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio de sua floresta ou domínio filho.
    
    c. Clique no **contêiner** Usuários no painel esquerdo e procure o grupo Universal **CsAdministrator** no painel direito. Se CsAdministrator (entre outros novos grupos Universais que começam com Cs) estiver presente, a replicação do Active Directory terá sido bem-sucedida.
    
    d. Se os grupos ainda não estão presentes, você pode forçar a replicação ou aguardar 15 minutos e atualizar o painel lateral direito. A replicação está completa quando os grupos estiverem presentes.
    
8. **Etapa 5: Preparar o domínio atual**
    
    a. Revise as informações de pré-requisitos da Etapa 5.
    
    b. Clique **em** Executar na Etapa 5 para iniciar o assistente Preparar Domínio Atual.
    
    c. Observe que o procedimento só deve ser executado uma vez para cada domínio na implantação e clique em **Próximo.**
    
    d. Depois que o domínio tiver sido preparado, você poderá exibir o log clicando em **Exibir Log.** 
    
    e. Clique **em Concluir** para fechar o assistente Preparar Domínio Atual e retorne às etapas Preparar Active Directory.
    
    Essas etapas devem ser concluídas em todos os domínios onde os objetos do Skype for Business Server são encontrados, caso contrário, os serviços podem não iniciar. Isso inclui qualquer tipo de objeto do Active Directory, como usuários, objetos de contato, grupos administrativos ou qualquer outro tipo de objeto. Você pode usar Set-CsUserReplicatorConfiguration -ADDomainNamingContextList para adicionar somente os domínios com objetos do Skype for Business Server, se necessário.
    
9. **Etapa 6: Verificar a replicação no domínio**
    
    a. Clique no **Shell de Gerenciamento do Skype for Business Server** na página **Aplicativos** para iniciar o PowerShell.
    
    b. Use o comando Get-CsAdDomain para verificar a replicação dentro do domínio.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Se você não especificar o parâmetro Domínio, o valor é configurado para o domínio local. 
  
    Exemplo de execução do comando para o domínio contoso.local:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Usando o parâmetro GlobalSettingsDomainController, você pode indicar onde as configurações globais estão armazenadas. Se suas configurações são armazenadas no contêiner Sistema (o que é comum em implantações de atualização que não tiveram a configuração global migrada para o contêiner Configuração), defina um controlador de domínio na raiz da floresta do AD DS. Se as configurações globais estiverem no contêiner Configuração (o que é típico nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você define qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e se referirá a qualquer controlador de domínio no Active Directory. 
  
    c. Se o resultado for **LC_DOMAINSETTINGS_STATE_READY**, o domínio foi replicado com êxito.
    
10. **Etapa 7: Adicionar usuários para fornecer acesso administrativo ao Painel de Controle do Skype for Business Server**
    
    a. Faça logon como membro do grupo Admins. de Domínio ou do grupo RTCUniversalServerAdmins.
    
    b. Abra Usuários e Computadores do **Active Directory,** expanda seu domínio, clique no contêiner **Usuários,** clique com o botão direito do mouse em CSAdministrator e escolha **Propriedades.**
    
    c. Em **Propriedades de CSAdministrator**, clique na guia **Membros**.
    
    d. Na guia **Membros**, clique em **Adicionar**. Em **Selecionar Usuários, Contatos, Computadores, Contas de Serviço ou Grupos**, localize **Insira os nomes de objeto para seleção**. Digite os nomes de usuário ou nomes de grupo para adicionar ao grupo CSAdministrators. Clique em **OK**.
    
    e. Na guia **Membros,** confirme se os usuários ou grupos selecionados estão presentes. Clique em **OK**.
    
    > [!CAUTION]
    > O Painel de Controle do Skype for Business Server é uma ferramenta de controle de acesso baseada em função. A associação ao grupo CsAdministrator oferece a um usuário que está usando o Painel de Controle do Skype for Business Server controle total para todas as funções de configuração disponíveis. Há outras funções disponíveis que foram projetadas para funções específicas. Para obter detalhes sobre as funções disponíveis, consulte [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md) Observe que os usuários não devem estar habilitados para o Skype for Business Server para se serem membros dos grupos de gerenciamento. 
  
    > [!CAUTION]
    > Para ajudar a manter a segurança e a integridade do controle de acesso baseado em função, adicione usuários aos grupos que definem qual função o usuário desempenha no gerenciamento da implantação do Skype for Business Server. 
  
11. Faça logoff e faça logoff novamente no Windows para que seu token de segurança seja atualizado com o novo grupo de segurança do Skype for Business Server e, em seguida, reabra o Assistente de Implantação.
    
12. Verifique se você vê uma marca de seleção verde ao lado de **Preparar o Active Directory** para confirmar o sucesso, conforme mostrado na figura.
    
     ![Preparar o Active Directory Concluído.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Confira também
 
[Serviços de Domínio do Active Directory para Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
