---
title: ClS Logger for Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Resumo: Saiba como usar o Agente de Log Centralizado (CLS) no Skype for Business Server 2015.'
ms.openlocfilehash: 24db5a23a29f9ae91ef2c3cab351fe7ca8c93a32
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398795"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>ClS Logger for Skype for Business Server 2015
 
**Resumo:** Saiba como usar o Agente de Log Centralizado (CLS) no Skype for Business Server 2015.
  
O Agente de Log CLS é uma ferramenta que ajuda você a gerenciar logs gerados pelo Serviço de Log Centralizado.
  
## <a name="prerequisites"></a>Pré-requisitos

Para usar com êxito o Agente de Loger cls, você precisará certificar-se de que o seguinte seja verdadeiro:
  
- Você está usando a ferramenta em um computador que é membro do domínio em que o Serviço de Registro Em Log Centralizado (CLS) está sendo executado. No momento, a ferramenta não tem suporte em sessões remotas do PowerShell.
    
- O arquivo Default.tmx da pasta de rastreamento (a pasta onde os dados de rastreamento são capturados para o CLS) e o Snooper devem ser copiados para a mesma pasta em que a ferramenta Doger cls está instalada.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Verificar o Status do Log de um conjunto de pools/computadores

Use os seguintes comandos para verificar o status do registro em log:
  
1. Na guia "Cenários de Início/Parada", selecione um grupo de Pools e/ou Computadores no exibição de árvore de Topologia.
    
2. Clique no botão Status do Log.
    
3. Exibir a saída de comando na área Saída de Comando do PowerShell para saber mais sobre o status de registro em log dos Pools e/ou Computadores selecionados.
    
## <a name="start-an-existing-scenario"></a>Iniciar um cenário existente

Para iniciar um cenário existente:
  
1. Na guia "Cenários de Início/Parada", selecione um Cenário existente no menu suspenso Cenários.
    
2. Selecione um grupo de Pools e/ou Computadores na exibição de árvore de Topologia.
    
3. Clique no botão Iniciar Cenário. A interface do usuário será desabilitada até que a operação seja concluída. Isso pode ser lento em implantações grandes.
    
4. A interface do usuário será habilitada novamente depois que o Cenário tiver sido iniciado com êxito, os detalhes da ação também serão mostrados na área Saída de Comando do PowerShell.
    
5. A tarefa pode levar algum tempo antes de o registro em log ser coletado pelo CLS antes de quaisquer novos dados desse cenário.
    
## <a name="stop-an-existing-scenario"></a>Parar um cenário existente

Para parar um cenário existente:
  
1. Na guia "Cenários de Início/Parada", selecione um Cenário existente no menu suspenso Cenários.
    
2. Selecione um grupo de Pools e/ou Computadores na exibição de árvore de Topologia.
    
3. Clique no botão Parar Cenário. A interface do usuário será desabilitada até que a operação seja concluída. Isso pode ser lento em implantações grandes.
    
4. A interface do usuário será habilitada novamente depois que o Cenário tiver parado, os detalhes da ação também serão mostrados na área Saída de Comando do PowerShell.
    
![Início e parada do agente cls.](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Pesquisar logs

Para pesquisar logs, selecione a guia "Pesquisar Logs CLS" e clique no botão "Logs de Pesquisa" após preencher os campos exibidos, conforme descrito abaixo:
  
> **Pasta de Arquivo de Log** A pasta para salvar os resultados da pesquisa de log. (Obrigatório)
> 
> **Nível de log** Isso determina o nível mais baixo que será apurado nos resultados. Por exemplo, se Aviso estiver selecionado, somente Aviso, Erro e Fatal serão mostrados. O padrão é Depurar.
> 
> **Pools** Pools de computador para executar a pesquisa de log, esses são os nós pai do exibição de árvore. (Obrigatório)
> 
> **Computadores** Computadores individuais para executar a pesquisa de log, esses são todos os nós filho na exibição de árvore. (Obrigatório)
> 
> **Hora de início** O período de tempo em que o CLS consultará os logs. (Obrigatório)
> 
> **Hora de Término** O período em que o CLS para de consultar os logs. (Obrigatório)
> 
> **Componentes** Usado para selecionar quais componentes adicionar à consulta. (Opcional)
> 
> **ID de chamada** A ID de chamada de qualquer caixa de diálogo SIP a ser filtrada. Observação: este campo usa correspondência exata. (Opcional)
> 
> **ID da conferência** A ID da conferência de todas as conferências a serem filtradas. Observação: este campo usa correspondência exata. (Opcional)
> 
> **Endereço IP** O endereço IP que deve ser filtrado. Observação: este campo usa correspondência exata. (Opcional)
> 
> **IDs de correlação** Trace instruções que são logicamente vinculadas por essa ID. (Opcional)
> 
> **Telefone filtro de número** por número de telefone. (Opcional)
> 
> **URI SIP** Filtrar por URI SIP. (Opcional)
> 
> **Conteúdo da mensagem SIP contém** Filtrar pelo conteúdo da mensagem SIP, isso substring search within this field. (Opcional)
> 
> **Corresponder a qualquer** Pesquisa usando um OR lógico se verificado. O padrão é Exact match of all parameters.
> 
> **Ignorar logs de rede** Ignora a pesquisa de todos os logs de rede, se verificado.
    
![Logs de pesquisa do AGENTE CLS.](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Criar um cenário

1. Na guia **Editar Cenários** , clique no **botão Criar Cenário** .
    
    > [!NOTE]
    > A criação de um novo cenário clona a configuração do cenário selecionado no momento. Se você clicar **em Limpar Configurações** antes de criar um novo cenário, ele começará sem componentes e Sinalizadores selecionados.
  
2. Insira o nome do cenário que você deve criar e pressionar Digite tecla ou clique no botão Ok.
    
3. O novo cenário agora será criado. Após a criação bem-sucedida, o drop-down Cenários será selecionado com o Cenário recém-criado.
    
## <a name="modify-a-scenario"></a>Modificar um cenário

![ClS Logger Screen shot, edit scenarios.](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Na guia **Editar Cenários** , localizou o cenário desejado para modificar.
    
2. Faça as alterações desejadas nos componentes, níveis e sinalizadores.
    
3. Clique no **botão Salvar Cenário** .
    
4. Ao salvar com êxito o cenário, ele atualizará o painel de informações do cenário com a configuração atualizada.
    
## <a name="delete-a-scenario"></a>Excluir um cenário

1. Na guia **Editar Cenários** , selecione um Cenário existente no menu suspenso Cenários.
    
2. Clique **em Excluir Cenário** para excluir o cenário.
    
3. Depois de confirmar a ação, o cenário será excluído.
    

