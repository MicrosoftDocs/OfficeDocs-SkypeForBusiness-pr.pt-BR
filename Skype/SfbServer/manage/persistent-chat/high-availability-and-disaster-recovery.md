---
title: Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumo: Saiba como gerenciar o servidor de Chat persistente alto disponibilidade e recuperação de desastres em Skype para Business Server 2015.'
ms.openlocfilehash: 8bc80ff6a38238b81b658a7f4d9620dc3a56b9be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar o servidor de Chat persistente alto disponibilidade e recuperação de desastres em Skype para Business Server 2015.
  
Este tópico descreve como realizar failover e failback volta Persistent Chat Server. Antes de ler este tópico, não deixe de ler [Planejar para alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e Configure [alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business 2015 de servidor](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
## <a name="fail-over-persistent-chat-server"></a>Failover de servidor de Chat persistente

Failover para o servidor de Chat persistente foi projetado para ser principalmente um processo manual.
  
O procedimento de failover está com base na pressuposição de que o Centro de dados secundário é para cima e em execução, mas os serviços de servidor de Chat persistente onde se encontra o banco de dados primário do Chat persistente não estão completamente disponíveis, incluindo o seguinte:
  
- Persistent Chat Server banco de dados primário e o banco de dados de espelho Persistent Chat Server estão desativados.
    
- Skype para o servidor de Front End Business Server está inoperante.
    
O procedimento é baseado em duas etapas básicas:
  
- Recupere o Chat persistente banco de dados primário (mgc).
    
- Estabelecer o espelhamento para o novo banco de dados primário.
    
O Chat persistente conformidade banco de dados (mgccomp) não tiver feito um failover. O conteúdo deste banco de dados é transitório e é excluído como os processos do adaptador de conformidade dos dados. É sua responsabilidade, como administrador de Chat persistente, para gerenciar corretamente a saída do adaptador para evitar a perda de dados.
  
Para fazer failover do Servidor de Chat Persistente:
  
1. Remova o envio de logs do banco de dados Persistent Chat Server Backup envio de Log.
    
  - Usando o SQL Server Management Studio, conecte-se à instância do banco de dados onde o banco de dados do servidor de Chat persistente mgc de backup está localizado.
    
  - Abra uma janela Consulta para o banco de dados mestre.
    
  - Use o seguinte comando para remover o envio de logs:
    
  ```
  exec sp_delete_log_shipping_secondary_database mgc
  ```

2. Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.
    
3. Use qualquer backup de log de transação não aplicado na sequência para o banco de dados secundário. Para obter detalhes, consulte [como: aplicar um Backup do Log de transações (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Coloque o banco de dados mgc de backup online. Usando a janela Consulta que é exibida na etapa 1b, faça o seguinte:
    
  - Encerre todas as conexões com o banco de dados mgc, se houver:
    
  - **exec sp_who2** para identificar as conexões com o banco de dados mgc.
    
  - **kill \<spid\> ** para terminar estas conexões.
    
  - Coloque o banco de dados online:
    
  - **Restaurar Banco de Dados mgc com recuperação**.
    
5. No Skype do Shell de gerenciamento do servidor de negócios, use o comando **Set-CsPersistentChatState-Identity "service: atl-cs-001" - PoolState FailedOver** fazer failover para o banco de dados mgc backup. Não se esqueça de substituir o nome de domínio totalmente qualificado do seu pool de Chat Persistente por atl-cs-001.litwareinc.com.
    
    O banco de dados de backup mgc agora serve como o banco de dados primário.
    
6. No Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que agora serve como o banco de dados primário. Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho. Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração.
    
7. Defina os servidores ativos do servidor de Chat persistente. Do Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    > [!IMPORTANT]
    > Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados. 
  
    Neste ponto, o failover do banco de dados primário Persistent Chat Server para o banco de dados de backup do servidor de Chat persistente for concluída com êxito.
    
## <a name="fail-back-persistent-chat-server"></a>Falha do servidor de bate-papo persistente

Este procedimento descreve as etapas necessárias para recuperar de uma falha do servidor de Chat persistente e restabelecer as operações no data center principal.
  
Durante falha do servidor de Chat persistente, data center principal sofre interrupção completa e a principal e bancos de dados de espelho se tornar indisponíveis. O data center primário faz failover para o servidor de backup.
  
O procedimento a seguir restaura a operação normal após o backup do data center primário e a recompilação dos servidores. O procedimento pressupõe que o Centro de dados principal foi recuperado de interrupção total e que o banco de dados mgc e o banco de dados mgccomp foram recriados e reinstalados usando o construtor de topologia.
  
O procedimento também pressupõe que nenhum servidor espelho ou de backup novo tenha sido implantado durante o período de failover e que o único servidor implantado seja o de backup e seu servidor espelho, conforme definido anteriormente em Failover do Servidor de Chat Persistente.
  
Estas etapas foram criadas para recuperar a configuração como ela se encontrava antes do desastre que resultou no failover do servidor primário para o servidor de backup.
  
1. Desmarque todos os servidores da lista Persistent Chat Server Active Server usando o cmdlet **Set-CsPersistentChatActiveServer** a partir do Skype do Shell de gerenciamento do servidor de negócios. Isso interrompe todos os servidores de bate-papo persistente de se conectar ao banco de dados mgc e o banco de dados mgccomp durante o failback.
    
    > [!IMPORTANT]
    > O SQL Server agent no secundário Persistent Chat Server servidor Back-End deve estar executando em uma conta privilegiada. Em termos específicos, a conta deve incluir: 
  
   - Acesso de leitura ao compartilhamento de rede no qual os backups serão colocados.
    
   - Acesso para gravação ao diretório local específico em que os backups serão copiados.
    
2. Desabilite o espelhamento no banco de dados mgc de backup:
    
   - Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Espelhar**.
    
   - Clique em **Remover Espelhamento**.
    
   - Clique em **OK**.
    
   - Execute as mesmas etapas com o banco de dados mgccomp.
    
3. Faça backup do banco de dados mgc para que ele possa ser restaurado para o novo banco de dados primário:
    
   - Usando o SQL Server Management Studio, conecte-se à instância mgc de backup.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Fazer Backup**. A caixa de diálogo **Backup de Banco de Dados** será exibida.
    
   - Em **Tipo de backup**, selecione **Completo**.
    
   - Para **Componente de backup**, clique em **Banco de dados**.
    
   - Aceite o nome de conjunto de backup padrão sugerido em **Nome** ou insira outro nome para o conjunto de backup.
    
   -  * \<Opcional\> *  Em **Descrição**, digite uma descrição do conjunto de backup.
    
   - Remova o local de backup padrão da lista de destino.
    
   - Adicione um arquivo à lista usando o caminho para o local de compartilhamento estabelecido para o envio de logs. Esse caminho está disponível para o banco de dados primário e para o banco de dados de backup.
    
   - Clique em **OK** para fechar a caixa de diálogo e iniciar o processo de backup.
    
4. Restaure o banco de dados primário usando o banco de dados de backup criado na etapa anterior.
    
   - Usando o SQL Server Management Studio, conecte-se à instância mgc primária.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas**, aponte para **Restaurar** e clique em **Banco de Dados**. A caixa de diálogo **Restaurar Banco de Dados** será exibida.
    
   - Selecione **Do dispositivo**.
    
   - Clique no botão Procurar, que abrirá a caixa de diálogo **Especificar Backup**. Em **Mídia de backup**, selecione **Arquivo**. Clique em **Adicionar**, selecione o arquivo de backup criado na etapa 3 e clique em **OK**.
    
   - Em **Selecione os conjuntos de backup a serem restaurados**, selecione o backup.
    
   - Clique em **Opções** no painel **Selecionar uma página**.
    
   - Em **Opções de restauração**, selecione **Substituir o banco de dados existente**.
    
   - Em **Estado de recuperação**, selecione **Deixar o banco de dados pronto para uso**.
    
   - Clique em **OK** para iniciar o processo de restauração.
    
5. Configure o envio de Log do SQL Server para o banco de dados primário. Siga os procedimentos em [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para estabelecer o envio de logs do banco de dados mgc primária.
    
6. Defina os servidores ativos do servidor de Chat persistente. Do Skype do Shell de gerenciamento do servidor de negócios, use o cmdlet **Set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    > [!IMPORTANT]
    > Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados. 
  
Para restaurar o pool ao seu estado normal, execute o seguinte comando do Windows PowerShell:
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .
  

