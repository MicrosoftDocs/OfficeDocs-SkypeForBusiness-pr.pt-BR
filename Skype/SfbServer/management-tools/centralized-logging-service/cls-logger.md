---
title: Agente CLS para Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Resumo: saiba como usar o Agente de Log Centralizado (CLS) no Skype for Business Server 2015.'
ms.openlocfilehash: a24cdbffc4b7601d325cd132afb5a7cf137b54f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835231"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>Agente CLS para Skype for Business Server 2015
 
**Resumo:** Saiba como usar o Agente de Log Centralizado (CLS) no Skype for Business Server 2015.
  
O Agente CLS é uma ferramenta que ajuda você a gerenciar logs gerados pelo Serviço de Log Centralizado.
  
## <a name="prerequisites"></a>Pré-requisitos

Para usar o Agente CLS com êxito, você precisará se certificar de que o seguinte seja verdadeiro:
  
- Você está usando a ferramenta em um computador que é membro do domínio no qual o Serviço de Log Centralizado (CLS) está sendo executado. No momento, a ferramenta não tem suporte em sessões do PowerShell Remoto.
    
- O arquivo Default.tmx da pasta de rastreamento (a pasta onde os dados de rastreamento são capturados para o CLS) e o Snooper devem ser copiados para a mesma pasta em que a ferramenta Agente CLS está instalada.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Verificar o status do registro em log de um conjunto de pools/computadores

Use os seguintes comandos para verificar o status do log:
  
1. Na guia "Iniciar/Parar Cenários", selecione um grupo de Pools e/ou Computadores na exibição de árvore de Topologia.
    
2. Clique no botão Status do Log.
    
3. Exibir a saída do comando na área de Saída de Comando do PowerShell para informações específicas sobre o status de log dos Pools e/ou Computadores selecionados.
    
## <a name="start-an-existing-scenario"></a>Iniciar um cenário existente

Para iniciar um cenário existente:
  
1. Na guia "Iniciar/Parar Cenários", selecione um Cenário existente no menu suspenso Cenários.
    
2. Selecione um grupo de Pools e/ou Computadores na exibição de árvore de Topologia.
    
3. Clique no botão Iniciar Cenário. A interface do usuário será desabilitada até que a operação seja concluída. Isso pode ser lento em grandes implantações.
    
4. A interface do usuário será habilitada novamente assim que o Cenário for iniciado com êxito, os detalhes da ação também serão mostrados na área de Saída de Comando do PowerShell.
    
5. A tarefa pode levar algum tempo antes de o registro em log ser coletado pelo CLS antes de quaisquer novos dados desse cenário.
    
## <a name="stop-an-existing-scenario"></a>Parar um cenário existente

Para interromper um cenário existente:
  
1. Na guia "Iniciar/Parar Cenários", selecione um Cenário existente no menu suspenso Cenários.
    
2. Selecione um grupo de Pools e/ou Computadores na exibição de árvore de Topologia.
    
3. Clique no botão Parar Cenário. A interface do usuário será desabilitada até que a operação seja concluída. Isso pode ser lento em grandes implantações.
    
4. A interface do usuário será habilitada novamente depois que o Cenário parar, os detalhes da ação também serão mostrados na área de Saída de Comando do PowerShell.
    
![Início e parada do Agente CLS](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Pesquisar logs

Para pesquisar logs, selecione a guia "Pesquisar Logs CLS" e clique no botão "Logs de Pesquisa" depois de preencher os campos exibidos conforme descrito abaixo:
  
> **Pasta do Arquivo de Log** A pasta para salvar os resultados da pesquisa de log. (Obrigatório)
> 
> **Nível de log** Isso determina o nível mais baixo que será aparecer nos resultados. Por exemplo, se Aviso estiver selecionado, somente Aviso, Erro e Fatal serão mostrados. O padrão é Depurar.
> 
> **Pools** Pools de computadores para realizar a pesquisa de log, esses são os nós pai do ponto de vista de árvore. (Obrigatório)
> 
> **Computadores** Computadores individuais para realizar a pesquisa de log, esses são todos os nós filhos na exibição de árvore. (Obrigatório)
> 
> **Hora de Início** O período em que o CLS consultará os logs. (Obrigatório)
> 
> **Hora de Término** O período em que o CLS interromperá a consulta dos logs. (Obrigatório)
> 
> **Componentes** Usado para selecionar quais componentes adicionar à consulta. (Opcional)
> 
> **ID da chamada** A ID de chamada de qualquer caixa de diálogo SIP a ser filtrada. Observe que esse campo usa correspondência exata. (Opcional)
> 
> **ID de conferência** A ID de conferência de qualquer conferência pela a ser filtrada. Observe que esse campo usa correspondência exata. (Opcional)
> 
> **Endereço IP** O endereço IP que será filtrado. Observe que esse campo usa correspondência exata. (Opcional)
> 
> **IDs de correlação** Instruções de rastreamento que são vinculadas logicamente por essa ID. (Opcional)
> 
> **Número de Telefone** Filtrar por número de telefone. (Opcional)
> 
> **URI do SIP** Filtrar por URI do SIP. (Opcional)
> 
> **Conteúdo da mensagem SIP contém** Filtrar por conteúdo de mensagem SIP, isso substring pesquisa dentro desse campo. (Opcional)
> 
> **Corresponder a qualquer** Pesquisa usando um OR lógico se estiver marcado. O padrão é a exact match de todos os parâmetros.
> 
> **Ignorar logs de rede** Ignora a pesquisa de todos os logs de rede, se estiver marcado.
    
![Logs de pesquisa do Agente cls](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Criar um cenário

1. Na guia **Editar Cenários,** clique no **botão Criar Cenário.**
    
    > [!NOTE]
    > Criar um novo cenário clona a configuração do cenário atualmente selecionado. Se você clicar em **Limpar Configurações** antes de criar um novo cenário, ele começará sem componentes e Sinalizadores selecionados.
  
2. Insira o nome do cenário que você criará e pressione a tecla Enter ou clique no botão Ok.
    
3. O novo cenário agora será criado. Após a criação bem-sucedida, o drop-down Cenários será selecionado com o Cenário recém-criado.
    
## <a name="modify-a-scenario"></a>Modificar um cenário

![Captura de tela do Agente CLS, editar cenários](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Na guia **Editar Cenários,** encontre o cenário desejado a ser modificado.
    
2. Faça as alterações desejadas nos componentes, níveis e sinalizadores.
    
3. Clique no **botão Salvar Cenário.**
    
4. Ao salvar o cenário com êxito, ele atualizará o painel de informações do cenário com a configuração atualizada.
    
## <a name="delete-a-scenario"></a>Excluir um cenário

1. Na guia **Editar Cenários,** selecione um Cenário existente no menu suspenso Cenários.
    
2. Clique **em Excluir Cenário** para excluir o cenário.
    
3. Depois de confirmar a ação, o cenário será excluído.
    

