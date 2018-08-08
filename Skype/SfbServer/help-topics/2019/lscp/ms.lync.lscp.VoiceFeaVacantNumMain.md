---
title: Número de Telefone Não Atribuído
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 082c7e5ebccec1c2f74304bc5117ed99ef9b0da1
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138427"
---
# <a name="unassigned-phone-number"></a>Número de Telefone Não Atribuído

> [!NOTE]
> UM do Exchange permanece disponível na Skype para Business Server 2019 ao integrar Skype para negócios 2019 com Exchange 2013 ou 2016 do Exchange. Devido às alterações no suporte no Exchange 2019, a integração de UM do Exchange está sendo desprovisionamento emphasised em favor de recursos de caixa postal de nuvem e atendedor automático de nuvem.  
 
Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
  
Como configurar a tabela de números não atribuídos dependerá de como você deseja usá-la. Você pode configurar a tabela com todas as extensões válidas para a sua organização, somente com extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuídos pode incluir ambos, números atribuídos e não atribuídos, mas será invocada somente quando um chamador discar um número que não esteja atribuído atualmente. Se você incluir todas as extensões válidas na tabela de números não atribuídos, pode especificar a ação que ocorre sempre que alguém sair da sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, pode ajustar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao cliente, poderá incluir o número do atendimento ao cliente antigo na tabela e atribuí-lo a um comunicado que fornece o novo número.
  
> [!IMPORTANT]
> Antes de configurar a tabela de números atribuídos, você já precisa ter definido um ou mais anúncios ou configurado um Atendedor Automático do UM do Exchange. 
  
A página **Número Não Atribuído** exibe uma lista de números não atribuídos definidos para sua organização.
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Número Não Atribuído**:
  
- Criar um novo intervalo de números não atribuídos
    
- Alterar um intervalo de números não atribuídos existente
    
- Excluir um intervalo de números não atribuídos
    
- Alterar a ordem dos intervalos de números não atribuídos a fim de determinar qual ação deve ser aplicada primeiro a uma chamada de entrada que corresponde a um número não atribuído. 
    
## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.
  
- **Novo** Inicia um novo intervalo de números não atribuído.
    
- **Editar** Abre o intervalo de números não atribuído selecionado para edição, seleciona todos os intervalos de números não atribuídos na lista ou exclui o intervalo de números não atribuído selecionado.
    
- **Mover para cima** Move o intervalo de números não atribuído selecionado para cima na lista, de forma que Skype para Business Server localiza-lo com antecedência e aplica-se a ação especificada antes de aplicar as ações especificadas para outros intervalos na lista.
    
    > [!NOTE]
    > Skype para Business Server procura na tabela de número não atribuída de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído. Por exemplo, se você tiver um intervalo que especifica uma ação de última instância, certifique-se de que o intervalo esteja no final da lista. 
  
- **Mover para baixo** Move o intervalo de números não atribuído selecionado para baixo na lista.
    
- **Confirmar tudo** Salva todas as alterações feitas a intervalos de números não atribuídos.
    
    > [!IMPORTANT]
    > Esse comando salva todas as alterações feitas na página  **Novo Número Não Atribuído** e na página **Editar Número Não Atribuído**.
  
- **Atualizar** Atualiza a lista de intervalos de números não atribuídos.
    
A lista a seguir descreve os campos na página.
  
- **Nome** O nome exclusivo que identifica o intervalo de números não atribuído.
    
- **Estado** Mostra quais intervalos de números foram salvos para o banco de dados e quais não foram.
    
- **Intervalo inicial** O número inicial do intervalo de números não atribuído.
    
- **Intervalo final** O número final do intervalo de números não atribuído.
    
- **Destino** A ID de serviço do serviço aplicativo que hospeda o aplicativo de anúncio que lidará com as chamadas de entrada para esse intervalo de números não atribuídos.
    
- **Comunicado** O comunicado que será reproduzido para esse intervalo de números não atribuídos.
    
Para obter detalhes sobre o comunicado recursos e capacidades, consulte o [plano para o aplicativo de anúncio no Skype para negócios](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação de planejamento. Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configurar o roteamento de números não atribuídos telefone](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação operações.
  

