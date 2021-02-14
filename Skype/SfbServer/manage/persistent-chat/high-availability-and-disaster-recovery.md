---
title: Gerenciar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumo: Saiba como gerenciar a alta disponibilidade e a recuperação de desastres do Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815041"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar a alta disponibilidade e a recuperação de desastres do Servidor de Chat Persistente no Skype for Business Server 2015.
  
Este tópico descreve como fazer fail over e fail back do Servidor de Chat Persistente. Antes de ler este tópico, certifique-se de ler Plano para alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e configurar alta disponibilidade e recuperação de desastre para o Servidor de Chat Persistente no Skype for Business Server [2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Fail over Persistent Chat Server

O failover para Servidor de Chat Persistente foi projetado para ser principalmente um processo manual.
  
O procedimento de failover baseia-se na suposição de que o data center secundário está em funcionamento, mas os serviços do Servidor de Chat Persistente onde o banco de dados de Chat Persistente principal está localizado estão completamente indisponíveis, incluindo o seguinte:
  
- O banco de dados primário do Servidor de Chat Persistente e o banco de dados espelho do Servidor de Chat Persistente estão inoídos.
    
- O Servidor front-end do Skype for Business Server está ino mesmo.
    
O procedimento é baseado em duas etapas básicas:
  
- Recupere o banco de dados de Chat Persistente primário (mgc).
    
- Estabelecer o espelhamento para o novo banco de dados primário.
    
O banco de dados de conformidade do Chat Persistente (mgccomp) não é failed over. O conteúdo deste banco de dados é temporário e é excluído como os processos do adaptador de conformidade dos dados. É sua responsabilidade, como Administrador de Chat Persistente, gerenciar corretamente a saída do adaptador para evitar a perda de dados.
  
Para fazer fail over do Servidor de Chat Persistente:
  
1. Remova o envio de log do banco de dados de Envio de Log de Backup do Servidor de Chat Persistente.
    
   - Usando o SQL Server Management Studio, conecte-se à instância do banco de dados onde o banco de dados mgc de backup do Servidor de Chat Persistente está localizado.
    
   - Abra uma janela de consulta para o banco de dados principal.
    
   - Use o seguinte comando para derrubar o envio de log:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.
    
3. Aplique qualquer backup do log de transação não aplicado na sequência para o banco de dados secundário. Para obter detalhes, [consulte Como: aplicar um backup do log de transações (Transact-SQL).](https://go.microsoft.com/fwlink/p/?linkid=247428)
    
4. Coloque o banco de dados de gerenciamento de backup online. Usando a janela de consulta que abra na etapa 1b, faça o seguinte:
    
   - Finalize todas as conexões com o banco de dados de gerenciamento, se houver:
    
   - **exec sp_who2** para identificar conexões com o banco de dados mgc.
    
   - **kill \<spid\>** para finalizar essas conexões.
    
   - Coloque o banco de dados online:
    
   - **restaurar banco de dados mgc com recuperação**.
    
5. No Shell de Gerenciamento do Skype for Business Server, use o comando **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** para fazer failover para o banco de dados de backup mgc. Não deixe de substituir o nome de domínio totalmente qualificado do seu pool de Chat Persistente por atl-cs-001.litwareinc.com.
    
    O banco de dados de backup de gerenciamento agora serve como o banco de dados primário.
    
6. No Shell de Gerenciamento do Skype for Business Server, use o cmdlet **Install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que agora serve como o banco de dados primário. Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho. Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração.
    
7. Definir os servidores ativos do Servidor de Chat Persistente. No Shell de Gerenciamento do Skype for Business Server, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    > [!IMPORTANT]
    > Todos os servidores ativos devem estar localizados dentro do mesmo centro de dados que o novo banco de dados primário ou em um centro de dados que possui uma conexão de baixa latência/alta largura de banda para o banco de dados. 
  
    Neste ponto, o failover do banco de dados primário do Servidor de Chat Persistente para o banco de dados de backup do Servidor de Chat Persistente é concluído com êxito.
    
## <a name="fail-back-persistent-chat-server"></a>Fail back do Servidor de Chat Persistente

Este procedimento descreve as etapas necessárias para se recuperar de uma falha do Servidor de Chat Persistente e restabelecer as operações do data center principal.
  
Durante a falha do Servidor de Chat Persistente, o data center primário sofre uma indisponibilização completa e os bancos de dados primário e espelho ficam indisponíveis. O data center primário faz failover para o servidor de backup.
  
O procedimento a seguir restaura a operação normal após o backup do data center primário e a recomposição dos servidores. O procedimento supõe que o data center primário foi recuperado da paralisação total e que o banco de dados mgc e o banco de dados mgccomp foram recompilados e reinstalados usando o Construtor de Topologias.
  
O procedimento também pressupo que nenhum servidor espelho e backup novo foi implantado durante o período de failover e que o único servidor implantado é o servidor de backup e seu servidor espelho, conforme definido anteriormente em Failover do Servidor de Chat Persistente.
  
Estas etapas foram criadas para recuperar a configuração como ela se encontrava antes do desastre que resultou no failover do servidor primário para o servidor de backup.
  
1. Limpe todos os servidores da lista do Servidor Ativo de Chat Persistente usando o cmdlet **Set-CsPersistentChatActiveServer** do Shell de Gerenciamento do Skype for Business Server. Isso impede que todos os Servidores de Chat Persistente se conectem ao banco de dados mgc e ao banco de dados mgccomp durante o failback.
    
    > [!IMPORTANT]
    > O agente do SQL Server no Servidor #A0 do Servidor de Chat Persistente secundário deve estar em execução em uma conta privilegiada. Em termos específicos, a conta deve incluir: 
  
   - Acesso de leitura ao compartilhamento de rede no qual os backups serão colocados.
    
   - Acesso de gravação ao diretório local específico em que os backups serão copiados.
    
2. Desabilite o espelhamento no banco de dados mgc de backup:
    
   - Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Espelhar**.
    
   - Click **Remover Espelhamento**.
    
   - Clique em **OK**.
    
   - Execute as mesmas etapas com o banco de dados mgccomp.
    
3. Faça backup do banco de dados mgc para que ele possa ser restaurado para o novo banco de dados primário:
    
   - Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Fazer Backup**. A caixa de diálogo **Backup de Banco de Dados** será exibida.
    
   - Em **Tipo de backup**, selecione **Completo**.
    
   - Para **Componente de backup**, clique em **Banco de dados**.
    
   - Aceite o nome de conjunto de backup padrão sugerido em **Nome** ou insira outro nome para o conjunto de backup.
    
   -  *\<Optional\>*  Em **Descrição,** insira uma descrição do conjunto de backup.
    
   - Remova o local de backup padrão da lista de destinos.
    
   - Adicione um arquivo à lista usando o caminho para o local de compartilhamento estabelecido para o envio de logs. Esse caminho está disponível para o banco de dados primário e para o banco de dados de backup.
    
   - Clique em **OK** para fechar a caixa de diálogo e iniciar o processo de backup.
    
4. Restaure o banco de dados primário usando o banco de dados de backup criado na etapa anterior.
    
   - Usando o SQL Server Management Studio, conecte-se à instância mgc principal.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas**, aponte para **Restaurar** e clique em **Banco de Dados**. A caixa de diálogo **Restaurar Banco de Dados** será exibida.
    
   - Selecione **Do dispositivo**.
    
   - Clique no botão "procurar", que abrirá a caixa de diálogo **Especificar Backup**. Em **Mídia de backup**, selecione **Arquivo**. Clique em **Adicionar**, selecione o arquivo de backup criado na etapa 3 e clique em **OK**.
    
   - Em **Selecione os conjuntos de backup a serem restaurados**, selecione o backup.
    
   - Clique em **Opções** no painel **Selecionar uma página**.
    
   - Em **Opções de restauração**, selecione **Substituir o banco de dados existente**.
    
   - Em **Estado de recuperação**, selecione **Deixar o banco de dados pronto para uso**.
    
   - Clique em **OK** para iniciar o processo de restauração.
    
5. Configure o envio de log do SQL Server para o banco de dados primário. Siga os procedimentos em [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.
    
6. Definir os servidores ativos do Servidor de Chat Persistente. No Shell de Gerenciamento do Skype for Business Server, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    > [!IMPORTANT]
    > Todos os servidores ativos devem estar localizados dentro do mesmo centro de dados que o novo banco de dados primário ou em um centro de dados que possui uma conexão de baixa latência/alta largura de banda para o banco de dados. 
  
Para restaurar o pool para seu estado normal, execute o seguinte comando do Windows PowerShell:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsPersistentChatState.](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)
  

