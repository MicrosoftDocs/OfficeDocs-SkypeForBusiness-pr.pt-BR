---
title: Atualizar para Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumo: saiba como atualizar do Lync Server 2013 para o Skype for Business Server 2015. Baixe uma avaliação gratuita do Skype for Business Server 2015 no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 02455d4c013f55363e173f16c9f4de60b71939d9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740077"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Atualizar para Skype for Business Server 2015
 
**Resumo:** Saiba como atualizar do Lync Server 2013 para o Skype for Business Server 2015. Baixe uma avaliação gratuita do Skype for Business Server 2015 no Centro [de Avaliação da Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Use os procedimentos neste documento para atualizar do Lync Server 2013 para o Skype for Business Server 2015 usando o Construtor de Topologias do Skype for Business Server e o novo recurso de atualização In-Place. Se você deseja atualizar do Lync Server 2010 ou do Office Communications Server 2007 R2, consulte [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> As atualizações in-locar estavam disponíveis no Skype for Business Server 2015, mas não são mais suportadas no Skype for Business Server 2019. Coexistência lado a lado é suportada, consulte [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.
  
## <a name="upgrade-from-lync-server-2013"></a>Atualização do Lync Server 2013

Atualizar o Lync Server 2013 para o Skype for Business Server 2015 envolve a instalação de softwares de pré-requisito, o uso do Construtor de Topologias do Skype for Business Server para atualizar bancos de dados no pool e o uso da atualização do Skype for Business Server In-Place em cada um dos servidores associados ao pool. Para concluir a atualização, vá pelas oito etapas deste tópico.
  
### <a name="before-you-begin"></a>Antes de começar

- Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Revisar [os requisitos do servidor Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Instalar pré-requisitos para Skype for Business Server 2015](install/install-prerequisites.md) .
    
- [Instale Skype for Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Etapa 1: Instalar ferramentas de administrador e baixar topologia

1. Conexão computador na topologia que não tenha o Lync OCSCore ou qualquer outro componente do Lync instalado.
    
2. A partir Skype for Business Server mídia de instalação 2015, executeSetup.exe **de** **OCS_Volume\Setup\AMD64**. 
    
3. Clique em **Instalar**. 
    
4. Aceitar o Contrato de Licença.
    
5. No Assistente de Implantação, clique em **Instalar ferramentas de administrador** e siga as etapas a serem instaladas.
    
     ![Captura de tela do Assistente de Implantação com link para as Ferramentas de Administrador de Instalação chamadas.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Na tela Windows Inicial, abra Skype for Business Server Construtor de Topologias.
    
7. Clique **em Baixar topologia da implantação existente** e clique em **Próximo**.
    
8. Insira um nome para a topologia e clique em **Salvar**.
    
9. Vá para o local onde você salvou a topologia e faça uma cópia da topologia.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Etapa 2: atualizar e publicar topologia usando o Construtor de Topologias

Antes de iniciar o processo de atualização, todos os serviços devem estar sendo executados para os pools que você planeja atualizar. Isso é para que as alterações de topologia sejam replicadas para o banco de dados local dos servidores no pool.
  
> [!IMPORTANT]
>  Salve uma cópia do arquivo de topologia antes de atualizar. Depois de atualizar, você não poderá rebaixar a topologia.> Se seus serviços estão nos mesmos servidores que seus bancos de dados, como o serviço de Chat Persistente está no mesmo servidor que o banco de dados de Chat Persistente, ignore esta etapa e vá para a etapa 4. Depois de interromper os serviços, execute a configuração In-Place Atualização em cada servidor para atualizar os bancos de dados locais.
  
> [!NOTE]
> Se a topologia tiver um banco de dados back-end espelhado, você verá os bancos de dados Principal e Espelhado aparecerem quando você publicar a **topologia** usando o Construtor de Topologias. Certifique-se de que todos os bancos de dados estão sendo executados na Entidade e selecione apenas a Entidade, não o espelho, ao publicar a topologia caso contrário, você verá um aviso depois de publicar a topologia.
  
Escolha uma das opções abaixo para atualizar e publicar uma nova topologia usando o Construtor de Topologias Skype for Business Server 2015. Depois de concluir as etapas e publicar a topologia atualizada, vá para a Etapa 3 neste tópico.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Opção 1: Atualizar um pool de Front-End isolado e os armazenamentos de Arquivamento e Monitoramento associados

Se o pool que você está atualizando tiver uma dependência do armazenamento de Arquivamento e Monitoramento, quando você usar as etapas a seguir, o armazenamento de Arquivamento e Monitoramento também será atualizado.
  
1. No Construtor de Topologias, clique com o botão direito do mouse em um pool do Lync Server 2013, selecione Atualizar para Skype for Business Server **2015** e siga as etapas. 
    
     ![Captura de tela do menu com o botão direito do mouse com a opção de atualização para o Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. No Construtor de Topologias, clique em  >  **Topologia de Ação Publicar** ou **Publicação** de  >    >  **Topologia de Ação.** 
    
     ![Captura de tela do menu Ação com a opção Publicar topologia no Construtor de Topologias.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Durante a publicação, escolha instalar um banco de dados no armazenamento de Arquivamento e Monitoramento.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Opção 2: Atualizar pool de front-end sem atualizar os armazenamentos de Arquivamento e Monitoramento

Se você usar as etapas a seguir, o arquivamento e o monitoramento do pool selecionado serão desabilitados. O pool não terá armazenamentos de Arquivamento e Monitoramento após a atualização.
  
1. No Construtor de Topologias, selecione o pool do Lync Server 2013 que você deseja atualizar.
    
2. Remova a dependência dos armazenamentos de Arquivamento e Monitoramento do Lync Server 2013. 
    
   - Vá até **Action**  >  **Edit properties**.
    
   - Des **limpar a caixa de seleção** Arquivamento.
    
     ![Captura de tela da caixa de seleção Arquivamento na caixa de diálogo Editar propriedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - **Desempure a caixa de seleção** Monitoramento.
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra a caixa de seleção Monitoramento.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Clique com o botão direito do mouse no pool do Lync Server 2013, selecione Atualizar para Skype for Business Server **2015** e siga as etapas. 
    
     ![Captura de tela do menu com o botão direito do mouse com a opção de atualização para o Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. No Construtor de Topologias, clique em  >  **Topologia de Ação Publicar** ou **Publicação** de  >    >  **Topologia de Ação.** 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Opção 3: Atualizar pool de front-end e associá-lo aos novos Skype for Business Server de Arquivamento e Monitoramento 2015

Se você usar as etapas a seguir, o arquivamento e o monitoramento serão parados no armazenamento anterior e começarão no novo armazenamento criado. 
  
1. No Construtor de Topologias, selecione o pool do Lync Server 2013 que você deseja atualizar. 
    
2. Remova a dependência dos armazenamentos de Arquivamento e Monitoramento do Lync Server 2013. 
    
   - Vá até **Action**  >  **Edit properties**.
    
   - Des **limpar a caixa de seleção** Arquivamento.
    
     ![Captura de tela da caixa de seleção Arquivamento na caixa de diálogo Editar propriedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - **Desempure a caixa de seleção** Monitoramento.
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra a caixa de seleção Monitoramento.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Clique com o botão direito do mouse no pool do Lync Server 2013, selecione Atualizar para Skype for Business Server **2015** e siga as etapas. 
    
     ![Captura de tela do menu com o botão direito do mouse com a opção de atualização para o Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Crie um novo SQL para Arquivamento. 
    
   - Selecione as propriedades pool e **Action**  >  **Edit**. 
    
   -  Marque a caixa de seleção **Arquivamento**.
    
   - Clique em **Novo**.
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostram Novo botão em Seção Arquivamento.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Crie um novo SQL para Monitoramento. 
    
   - Selecione as propriedades pool e **Action**  >  **Edit**. 
    
   -  Marque a **caixa de seleção** Monitoramento.
    
   - Clique em **Novo**.
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostram Novo botão em Seção Monitoramento.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. No Construtor de Topologias, clique em  >  **Topologia de Ação Publicar** ou **Publicação** de  >    >  **Topologia de Ação.** 
    
7. Durante a publicação, escolha instalar o banco de dados no novo armazenamento de Arquivamento e Monitoramento.
    
### <a name="step-3-wait-for-replication"></a>Etapa 3: Aguardar replicação

Dê algum tempo à replicação para publicar a topologia atualizada em todos os servidores do ambiente.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Etapa 4: Parar todos os serviços no pool a serem atualizados

Em cada servidor que esteja atendendo o pool que você vai atualizar, execute o seguinte cmdlet no PowerShell:
  
```powershell
Disable-CsComputer -Scorch
```

Recomendamos o uso Disable-CsComputer porque talvez seja necessário reiniciar o servidor durante o processo In-Place Atualização. Se você usar Stop-CsWindowsService, alguns serviços poderão ser reiniciados automaticamente após uma reinicialização. Isso pode fazer com que a atualização In-Place falha.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Etapa 5: Atualizar pools de front-end e servidores de pool não front-end

> [!NOTE]
>  Antes de atualizar, instale todos os novos pré-requisitos necessários para o Skype for Business Server 2015, que incluem:> Pelo menos 32 GB de espaço livre antes de tentar uma atualização. Além disso, certifique-se de que a unidade é uma unidade local fixa, não está conectada por USB ou Firewire, é formatado com o sistema de arquivos NTFS, não é compactado e não contém um arquivo de página.> PowerShell versão 6.2.9200.0 ou posterior.> A atualização cumulativa mais recente do Lync Server 2013 instalada.> SQL Server 2012 SP1 instalado.> O KB a seguir instalado (instalado automaticamente se estiver usando o Microsoft Update): > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
Use o In-Place Atualização em cada servidor para atualizar o pool de Front-End, Pool de Borda, Servidor de Mediação e o pool de Chat Persistente.
  
1. Em cada servidor, execute **Setup.exe** de **OCS_Volume\Setup\amd64** na mídia de instalação Skype for Business Server 2015.
    
2. Aceite o contrato de licença e siga os prompts para o In-Place Upgrade.
    
3. Repita estas etapas para cada servidor no pool de Front-End e em cada servidor de pool não Front-End.
    
> [!NOTE]
> Você pode ser solicitado a reiniciar o servidor durante a atualização In-Place Atualização. Está okey. Após a reinicialização, In-Place atualização continuará de onde ela foi deixada. 
  
Quando a In-Place Upgrade for concluída com êxito, você verá a seguinte mensagem.
  
![Captura de tela que mostra a atualização in-local concluída com êxito.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Etapa 6: Reiniciar serviços em todos os servidores atualizados

> [!NOTE]
> Antes de reiniciar os serviços, verifique se %ProgramData%\WindowsFabric não existe em todos os Servidores Front-End. Se existir, exclua-o antes de iniciar os serviços. 
  
- Depois de atualizar todos os servidores no pool de Front-End, reinicie os serviços usando o seguinte comando do PowerShell: 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > Se já houver uma reinicialização pendente do sistema necessária antes de começar a executar In-Place Atualização, o In-Place Upgrade não solicitará que você seja reiniciado no final da instalação. Isso fará com que algumas exceções de assembly sejam lançadas no primeiro servidor Front-End quando você tentar iniciar serviços usando o cmdlet Start-CSPool. Para resolver esses erros, reinicie todos os servidores no pool e execute o cmdlet novamente. 
  
- Nos servidores de pool que não são front-end, reinicie os serviços usando o seguinte comando:
    
  ```powershell
  Start-CsWindowsService
  ```

Depois de clicar **em OK** na página In-Place Atualização, você verá o lembrete a seguir para concluir esta etapa.
  
![Captura de tela que mostra as próximas etapas após a conclusão da atualização local com êxito.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Etapa 7: verificar se Skype for Business funcionalidade funciona

Para garantir que a atualização tenha sido bem-sucedida, para o pool que foi atualizado, teste Skype for Business para garantir que a funcionalidade está funcionando conforme o esperado. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Etapa 8: Atualizar pools secundários

Repita as etapas deste tópico para atualizar os pools adicionais que você tem em seu ambiente.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Solucionar problemas com o In-Place Upgrade

Se a atualização In-Place falha, você pode ver uma mensagem semelhante ao que está na imagem a seguir. 
  
![Captura de tela que mostra falha na atualização local porque uma atualização cumulativa necessária não está instalada.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Revise a mensagem completa na parte inferior da página para ajudá-lo a solucionar o problema. Clique **em Exibir logs** para obter mais detalhes.
  
Se a atualização do In-Place  falhar em Verificar a preparação da atualização ou a instalação de pré-requisitos **ausentes,** verifique se o servidor tem todas as atualizações mais recentes do Windows Server, do Lync Server e do SQL Server aplicadas, e todos os softwares e funções necessários estão instalados. Para uma lista do que é necessário, consulte Requisitos de [servidor para Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [Instalar pré-requisitos para Skype for Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Confira também

[Planejar a atualização para o Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Requisitos de servidor para Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Instalar pré-requisitos para o Skype for Business Server 2015](install/install-prerequisites.md)
  
[Instalar Skype for Business Server 2015](install/install.md)
