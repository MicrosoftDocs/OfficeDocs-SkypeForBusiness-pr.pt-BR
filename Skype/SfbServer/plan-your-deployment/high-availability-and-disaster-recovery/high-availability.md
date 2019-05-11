---
title: Alta disponibilidade e gerenciamento de Pool de Front-Ends
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Saiba mais sobre o gerenciamento de pool de Front-End do Skype para Business Server, incluindo o gerenciamento de pools, perda de quórum e etapas especiais para pools com apenas dois servidores Front-End.
ms.openlocfilehash: bab9d4b40132665719a1e9d019b8f34e2d96622d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910225"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidade e gerenciamento de Pool de Front-Ends
 
Saiba mais sobre o gerenciamento de pool de Front-End do Skype para Business Server, incluindo o gerenciamento de pools, perda de quórum e etapas especiais para pools com apenas dois servidores Front-End.
  
No Skype para Business Server, a arquitetura de pools de Front-End usa um modelo de sistemas distribuídos, com os dados de cada usuário mantidos em até três servidores de Front-End no pool. Recomendamos que todos os pools de Front End do Enterprise Edition incluem pelo menos três servidores Front-End. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planejando o gerenciamento de Pool de Front-Ends

 Skype para Business Server usa um modelo de sistemas distribuídos com base no Windows Fabric. Nesse modelo, os dados importantes para cada usuário e a conferência são armazenados em três servidores Front-End em um pool de Front-End. Esses três servidores de armazenamento de um determinado conjunto de dados são calledreplicas.
  
Com o modelo distribuído para pools de Front-End, um determinados números dos servidores de um pool devem estar executando para o pool funcione. Há dois modos de perda de um pool.
  
- Perda de quórum no nível do grupo de roteamento, causada por servidores de réplica insuficientes para um grupo de roteamento em particular. Um grupo de roteamento é um conjunto de usuários hospedados no pool. Cada grupo de roteamento tem três réplicas no pool: uma réplica primária e duas réplicas secundárias.
    
- Perda de quórum no nível do pool, causada quando um número insuficiente de servidores de propagação está em execução no pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perda de quórum no nível do grupo de roteamento

A primeira vez que você iniciar um novo Pool de Front-Ends, é essencial que 85% dos servidores estejam em execução, conforme exibido na tabela a seguir. Se menos servidores estiverem em execução, os serviços poderão ficar parados no estado inicial e o pool pode não iniciar.
  
|Número total de servidores no pool  <br/> |Número de servidores que devem estar em execução para que o pool seja iniciado na primeira vez  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|8  <br/> |6  <br/> |
|9  <br/> |7  <br/> |
|10  <br/> |8  <br/> |
|11  <br/> |9  <br/> |
|12  <br/> |10  <br/> |
   
Cada vez subsequente que o pool for iniciado, 85% dos servidores devem ser iniciados (conforme exibido na tabela anterior). Se esse número de servidores não pode ser iniciado (mas podem ser iniciados servidores suficientes para que você não estiver na perda de quórum de nível do pool), você pode usar o `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet para permitir que o pool recuperar-se de que essa perda de quórum de nível de grupo roteamento e fazer o progresso. Para obter mais informações sobre como usar esse cmdlet, consulte <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> Em pools com um número par de servidores, o Skype for Business Server usa o banco de dados SQL primário como testemunha. Em um pool como esse, se você desligar o banco de dados primário, alternar para a cópia Espelho e desligar alguns servidores Front-End, de modo que o número de servidores em execução seja insuficiente, de acordo com a tabela anterior, todo o pool será desligado. Para obter mais informações, consulte [A testemunha de espelhamento de banco de dados](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perda de quórum no nível do pool

Para um pool de Front-End funcionar nisso, ele não pode ser em perda de quórum de nível do pool. Se o número de servidores em execução estiver abaixo do nível funcional conforme exibido na tabela anterior, os servidores restantes no pool interromperão todos os serviços do Skype for Business Server. Observe que os números na tabela a seguir pressupõem que os servidores Back-End no pool estejam em execução.
  
|Número total de servidores Front-End do pool  <br/> |Número de servidores que devem estar em execução para o pool ser funcional  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Qualquer um dos 2  <br/> |
|5-6  <br/> |Qualquer um dos 3  <br/> |
|7  <br/> |Qualquer um dos 4  <br/> |
|8-9  <br/> |Qualquer um dos 4 dos 7 primeiros servidores  <br/> |
|10-12  <br/> |Qualquer um dos 5 dos 9 primeiros servidores  <br/> |
   
Na tabela anterior, "servidores primeiro" são os servidores que foram levados pela primeira vez, em ordem cronológica, quando o pool foi iniciado pela primeira vez. Para determinar a esses servidores, você pode usar o `Get-CsComputer` cmdlet com o ` -PoolFqdn` opção. Esse cmdlet exibirá os servidores na ordem em que aparecem na topologia, e aqueles que aparecem no topo da lista são os primeiros servidores.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Etapas adicionais para garantir que os pools sejam funcionais

Observe alguns outros fatores para garantir que seus Pools de Front-Ends permaneçam funcionais.
  
- Quando você mover usuários para o pool pela primeira vez, certifique-se pelo menos que três dos servidores Front-End estão em execução.
    
- Se você estabelecer um relacionamento de emparelhamento entre este e um outro pool para fins de recuperação de desastres, após estabelecer esse relacionamento você deve garantir que o pool tenha três servidores Front-End em execução simultânea em algum momento para sincronizar adequadamente os dados com o pool de backup. Para obter mais informações sobre os recursos de recuperação de desastres e pareamento do pool, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool de Front-Ends com dois servidores Front-End

Não é recomendável implantar um pool de Front-End que contém apenas dois servidores Front-End. Esse pequeno pool não fornecerá uma solução robusta de alta disponibilidade como um pool maior faria e demandará um gerenciamento mais cuidadoso. Além disso, se o servidor Back-End de um pool de dois servidores ficaram inativos, o próprio pool inteiro seria provavelmente breve descer na também. Se você desejar implantar apenas um ou dois servidores que executam o Skype para Business Server, é recomendável que implantá-los como servidores Standard Edition.
  
Se você precisar implantar um pool com dois servidores Front-End, siga estas diretrizes:
  
- Se um dos dois servidores Front-End ficar inativo, você deve tentar colocar o servidor com falha backup assim que você pode. Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.
    
- Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:
    
  - A prática recomendada é reiniciar ambos os servidores Front-End ao mesmo tempo. 
    
  - Se os dois servidores não podem ser reiniciados ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.
    
  - Se você não puder ativá-los backup nesta ordem, use o seguinte cmdlet antes de colocar o pool de backup:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Falhas e alterações na configuração do Pool de Front-Ends

Se um servidor Front-End falhar e não puder ser substituído em alguns dias ou mais, remova o servidor da topologia. Adicione o novo servidor Front-End à topologia quando estiver disponível novamente.
  
Sempre que fizer uma alteração na configuração de um Pool de Front-Ends, como adicionar ou remover servidores, você deve seguir estas diretrizes:
  
- Após a publicação da nova topologia, você deve reiniciar cada servidor Front-End no pool. Reinicie todos, um de cada vez.
    
- Se todo o pool ficou desativado durante a alteração de configuração, execute o seguinte cmdlet depois que a nova topologia é publicada:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

