---
title: Agente CLS do Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/25/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Resumo: Saiba como usar o registro de serviço de registro em log centralizado (CLS) no Skype para Business Server 2015.'
ms.openlocfilehash: 24b4d873694088b371a4db203c0081f7e9a8f493
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>Agente CLS do Skype for Business Server 2015
 
**Resumo:** Saiba como usar o registro de serviço de registro em log centralizado (CLS) no Skype para Business Server 2015.
  
O Agente CLS é uma ferramenta que ajuda você a gerenciar os logs gerados pelo Centralized Logging Service.
  
## <a name="prerequisites"></a>Pré-requisitos

Para usar o Agente CLS com êxito, você precisará garantir que o seguinte seja verdadeiro:
  
- Você está usando a ferramenta em um computador que é membro do domínio no qual o Centralized Logging Service (CLS) está sendo executado. Atualmente a ferramenta não é compatível com as sessões do Remote PowerShell.
    
- O arquivo Default.tmx da pasta de rastreamento (a pasta para a qual são capturados os dados de rastreamento do CLS) e o Snooper devem ser copiados para a mesma pasta em que a ferramenta Agente CLS está instalada.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Verificar o status do registro no log de diversos pools/computadores

Use os comandos a seguir para verificar o status do registro em log:
  
1. Na guia "Iniciar/Parar cenários", selecione um agrupamento de Pools e/ou em computadores no modo de exibição de árvore da topologia.
    
2. Clique no botão Status do registro em log.
    
3. Veja o resultado do comando na área Resultado do comando de PowerShell para obter dados específicos sobre o status do registro em log dos pools e/ou computadores selecionados.
    
## <a name="start-an-existing-scenario"></a>Iniciar um cenário existente

Para iniciar um cenário existente:
  
1. Na guia "Iniciar/Parar cenários", selecione um cenário existente no menu suspenso cenários.
    
2. Selecione um agrupamento de Pools e/ou Computadores no modo de exibição de árvore Topologia.
    
3. Clique no botão Iniciar cenário. A interface do usuário ficará desativada até que a operação seja concluída. Pode haver lentidão em grandes implantações.
    
4. A interface do usuário será habilitada novamente quando o cenário tiver sido iniciado com êxito, e os detalhes da ação também serão exibidos na área de Resultados do Comando do PowerShell.
    
5. A tarefa pode levar alguns momentos antes de o registro em log ser pego pelo CLS antes de qualquer dado novo deste cenário.
    
## <a name="stop-an-existing-scenario"></a>Interromper um cenário existente

Para interromper um cenário existente:
  
1. Na guia "Iniciar/Parar cenários", selecione um cenário existente no menu suspenso cenários.
    
2. Selecione um agrupamento de Pools e/ou Computadores no modo de exibição de árvore Topologia.
    
3. Clique no botão Iniciar cenário. A interface do usuário ficará desativada até que a operação seja concluída. Pode haver lentidão em grandes implantações.
    
4. A interface do usuário será habilitada novamente quando o cenário tiver sido interrompido, e os detalhes da ação também serão exibidos na área de Resultados do Comando do PowerShell.
    
![Início e parada do CLS Logger](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Pesquisar logs

Para pesquisar por logs, selecione a guia "Pesquisa CLS Logs" e clique no botão "Pesquisar Logs" depois de preencher os campos exibidos, conforme descrito a seguir:
  
> **Pasta do arquivo de log** A pasta na qual os resultados da pesquisa do log são salvos. (Obrigatório)
    
> **Nível do log** Determina o nível mais baixo que será exibido nos resultados. Por exemplo: se for selecionado Aviso, serão exibidos somente Aviso, Erro e Fatal. O padrão é Depuração.
    
> **Pools** Pools de computador para executar a pesquisa de logs. Tratam-se dos nós pais no modo de exibição de árvore. (Obrigatório)
    
> **Computadores** Cada computador para a execução da pesquisa de logs. Todos são nós filhos no modo de exibição de árvore. (Obrigatório)
    
> **Hora de início** O período no qual o CLS consultará os logs. (Obrigatório)
    
> **Hora de fim** O período no qual o CLS interromperá a consulta dos logs. (Obrigatório)
    
> **Componentes** Usados para selecionar quais componentes adicionar à consulta. (Opcional)
    
> **ID da chamada** O ID da chamada de qualquer diálogo do SIP pelo qual ser filtrado. Observe que esse campo usa correspondência exata. (Opcional)
    
> **ID de conferência** O ID de conferência de todas as conferências a serem filtradas. Observe que esse campo usa correspondência exata. (Opcional)
    
> **Endereço IP** O endereço IP para ser filtrado. Observe que esse campo usa correspondência exata. (Opcional)
    
> **IDs de correlação** Instruções de rastreamento que são vinculadas logicamente por essa ID. (Opcional)
    
> **Número de telefone** Filtrar por número de telefone. (Opcional)
    
> **URI do SIP** Filtrar por URI do SIP. (Opcional)
    
> **Conteúdo da mensagem do SIP contém** Filtrar por conteúdo da mensagem do SIP; será uma pesquisa de substring dentro desse campo. (Opcional)
    
> **Corresponder qualquer** Pesquisa utilizando um OU lógico, se estiver marcado. O padrão é a correspondência exata de todos os parâmetros.
    
> **Ignorar logs de rede** Ignora a pesquisa pelos logs de rede, se estiver marcado.
    
![Registros de pesquisa do CLS Logger](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Criar um cenário

1. Na guia **Editar cenários** , clique no botão **Criar cenário** .
    
    > [!NOTE]
    > Criar um novo cenário clonará a configuração do cenário que está selecionado. Se você clicar em **Limpar Configurações** antes de criar um novo cenário, ele começará sem nenhum componente ou sinalizador selecionado.
  
2. Insira o nome do cenário que você deseja criar e pressione a tecla Enter ou clique no botão OK.
    
3. O novo cenário será criado. Quando a criação for bem-sucedida, a lista suspensa Cenários será selecionada com o novo cenário.
    
## <a name="modify-a-scenario"></a>Modificar um cenário

![Captura de tela do Agente CLS, editar cenários](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Na guia **Editar Cenários**, encontre o cenário que você deseja modificar.
    
2. Faça as mudanças desejadas nos componentes, níveis e sinalizadores.
    
3. Clique no botão **Salvar Cenário**.
    
4. Quando o cenário for salvo, o painel de informações será atualizado com as novas configurações.
    
## <a name="delete-a-scenario"></a>Excluir um cenário

1. Na guia **Editar Cenários**, selecione um cenário existente do menu suspenso Cenários.
    
2. Clique em **Excluir Cenário** para excluir o cenário.
    
3. Depois de confirmar a ação, o cenário será excluído.
    

