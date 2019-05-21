---
title: Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumo: saiba como gerenciar o servidor de chat persistente alta disponibilidade e recuperação de desastres no Skype for Business Server 2015.'
ms.openlocfilehash: 5cf0fc8ba175111a0e0760f4447bd309c34b759c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279302"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar a alta disponibilidade do servidor de chat persistente e a recuperação de desastres no Skype for Business Server 2015.
  
Este tópico descreve como fazer failover e failback do servidor de chat persistente. Antes de ler este tópico, certifique-se de ler [plano de alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e [Configurar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente no Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Fazer failover do servidor de chat persistente

O failover do servidor de chat persistente foi projetado para ser principalmente um processo manual.
  
O procedimento de failover baseia-se na pressuposição de que o centro de dados secundário está em funcionamento, mas os serviços persistentes do servidor de chat em que o banco de dados de chat persistente primário está localizado não estão disponíveis, incluindo o seguinte:
  
- Banco de dados persistente do servidor de chat e banco de dados persistente do servidor de chat persistente estão inativos.
    
- O servidor front-end do Skype for Business Server está inoperante.
    
O procedimento é baseado em duas etapas básicas:
  
- Recuperar o banco de dados de chat persistente primário (MGC).
    
- Estabelecer o espelhamento para o novo banco de dados primário.
    
O banco de dados de conformidade de chat persistente (mgccomp) não apresentou failover. O conteúdo deste banco de dados é transitório e é excluído como os processos do adaptador de conformidade dos dados. É sua responsabilidade, como administrador de chat persistente, gerenciar corretamente a saída do adaptador para evitar perda de dados.
  
Para fazer failover do Servidor de Chat Persistente:
  
1. Remova o envio de log do banco de dados de envio de log de backup persistente do servidor de chat.
    
   - Usando o SQL Server Management Studio, conecte-se à instância do banco de dados em que o banco de dados de backup do servidor de chat persistente MGC está localizado.
    
   - Abra uma janela Consulta para o banco de dados mestre.
    
   - Use o seguinte comando para remover o envio de logs:
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copie qualquer arquivo de backup não copiado do compartilhamento de backup para a pasta de destino da cópia do servidor de backup.
    
3. Use qualquer backup de log de transação não aplicado na sequência para o banco de dados secundário. Para obter detalhes, consulte [como aplicar um backup de log de transação (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Coloque o banco de dados mgc de backup online. Usando a janela Consulta que é exibida na etapa 1b, faça o seguinte:
    
   - Encerre todas as conexões com o banco de dados mgc, se houver:
    
   - **exec sp_who2** para identificar as conexões com o banco de dados mgc.
    
   - **eliminar \<spid\> ** para encerrar essas conexões.
    
   - Coloque o banco de dados online:
    
   - **Restaurar Banco de Dados mgc com recuperação**.
    
5. No Shell de gerenciamento do Skype for Business Server, use o comando **set-CsPersistentChatState-Identity "Service: ATL-cs-001.litwareinc.com"-poolstate FailedOver** para fazer failover para o banco de dados de backup do MGC. Não se esqueça de substituir o nome de domínio totalmente qualificado do seu pool de Chat Persistente por atl-cs-001.litwareinc.com.
    
    O banco de dados de backup mgc agora serve como o banco de dados primário.
    
6. No Shell de gerenciamento do Skype for Business Server, use o cmdlet **install-CsMirrorDatabase** para estabelecer um espelho de alta disponibilidade para o banco de dados de backup que agora funciona como o banco de dados principal. Use a instância do banco de dados de backup como o banco de dados primário e a instância do banco de dados de espelho de backup como a instância do espelho. Este não é o mesmo espelho do que aquele inicialmente configurado para o banco de dados primário durante a configuração.
    
7. Defina os servidores ativos do servidor de chat persistente. No Shell de gerenciamento do Skype for Business Server, use o cmdlet **set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    > [!IMPORTANT]
    > Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados. 
  
    Nesse ponto, o failover do banco de dados primário do servidor de chat persistente para o banco de dados de backup do servidor de chat persistente é concluído com êxito.
    
## <a name="fail-back-persistent-chat-server"></a>Fazer failback do servidor de chat persistente

Este procedimento descreve as etapas necessárias para recuperar-se de uma falha persistente do servidor de chat e para restabelecer as operações do data center principal.
  
Durante uma falha persistente do servidor de chat, o data center principal sofre uma interrupção completa, e os bancos de dados principal e espelho ficam indisponíveis. O data center primário faz failover para o servidor de backup.
  
O procedimento a seguir restaura a operação normal após o backup do data center primário e a recompilação dos servidores. O procedimento pressupõe que o principal centro de dados foi recuperada da interrupção total, e que o banco de dados MGC e o banco de dados do mgccomp foram recriados e reinstalados usando o construtor de topologias.
  
O procedimento também pressupõe que nenhum servidor espelho ou de backup novo tenha sido implantado durante o período de failover e que o único servidor implantado seja o de backup e seu servidor espelho, conforme definido anteriormente em Failover do Servidor de Chat Persistente.
  
Estas etapas foram criadas para recuperar a configuração como ela se encontrava antes do desastre que resultou no failover do servidor primário para o servidor de backup.
  
1. Desmarque todos os servidores da lista de servidores de chat persistentes usando o cmdlet **set-CsPersistentChatActiveServer** do Shell de gerenciamento do Skype for Business Server. Isso interrompe a conexão de todos os servidores de chat persistentes ao banco de dados do MGC e do banco de dados do mgccomp durante o failback.
    
    > [!IMPORTANT]
    > O agente do SQL Server no servidor back-end persistente do servidor de chat secundário deve estar em execução em uma conta privilegiada. Em termos específicos, a conta deve incluir: 
  
   - Acesso de leitura ao compartilhamento de rede no qual os backups serão colocados.
    
   - Acesso para gravação ao diretório local específico em que os backups serão copiados.
    
2. Desabilite o espelhamento no banco de dados mgc de backup:
    
   - Usando o SQL Server Management Studio, conecte-se à instância MGC de backup.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Espelhar**.
    
   - Clique em **Remover Espelhamento**.
    
   - Clique em **OK**.
    
   - Execute as mesmas etapas com o banco de dados mgccomp.
    
3. Faça backup do banco de dados mgc para que ele possa ser restaurado para o novo banco de dados primário:
    
   - Usando o SQL Server Management Studio, conecte-se à instância MGC de backup.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas** e clique em **Fazer Backup**. A caixa de diálogo **Backup de Banco de Dados** será exibida.
    
   - Em **Tipo de backup**, selecione **Completo**.
    
   - Para **Componente de backup**, clique em **Banco de dados**.
    
   - Aceite o nome de conjunto de backup padrão sugerido em **Nome** ou insira outro nome para o conjunto de backup.
    
   -  * \<\> Opcionais*  Em **Descrição**, digite uma descrição do conjunto de backup.
    
   - Remova o local de backup padrão da lista de destino.
    
   - Adicione um arquivo à lista usando o caminho para o local de compartilhamento estabelecido para o envio de logs. Esse caminho está disponível para o banco de dados primário e para o banco de dados de backup.
    
   - Clique em **OK** para fechar a caixa de diálogo e iniciar o processo de backup.
    
4. Restaure o banco de dados primário usando o banco de dados de backup criado na etapa anterior.
    
   - Usando o SQL Server Management Studio, conecte-se à instância principal do MGC.
    
   - Clique com o botão direito do mouse no banco de dados mgc, aponte para **Tarefas**, aponte para **Restaurar** e clique em **Banco de Dados**. A caixa de diálogo **Restaurar Banco de Dados** será exibida.
    
   - Selecione **Do dispositivo**.
    
   - Clique no botão Procurar, que abrirá a caixa de diálogo **Especificar Backup**. Em **Mídia de backup**, selecione **Arquivo**. Clique em **Adicionar**, selecione o arquivo de backup criado na etapa 3 e clique em **OK**.
    
   - Em **Selecione os conjuntos de backup a serem restaurados**, selecione o backup.
    
   - Clique em **Opções** no painel **Selecionar uma página**.
    
   - Em **Opções de restauração**, selecione **Substituir o banco de dados existente**.
    
   - Em **Estado de recuperação**, selecione **Deixar o banco de dados pronto para uso**.
    
   - Clique em **OK** para iniciar o processo de restauração.
    
5. Configurar o envio de log do SQL Server para o banco de dados principal. Siga os procedimentos em [Configurar a alta disponibilidade e a recuperação de desastre para o servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para estabelecer o envio de log para o banco de dados principal do MGC.
    
6. Defina os servidores ativos do servidor de chat persistente. No Shell de gerenciamento do Skype for Business Server, use o cmdlet **set-CsPersistentChatActiveServer** para definir a lista de servidores ativos.
    
    > [!IMPORTANT]
    > Todos os servidores ativos devem estar localizados no mesmo data center que o novo banco de dados primário ou em um data center que tenha uma conexão de baixa latência/alta largura de banda com o banco de dados. 
  
Para restaurar o pool para seu estado normal, execute o seguinte comando do Windows PowerShell:
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Para obter mais informações, consulte o tópico da ajuda referente ao cmdlet do [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).
  

