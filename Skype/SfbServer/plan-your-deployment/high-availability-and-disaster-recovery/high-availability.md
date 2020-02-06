---
title: Alta disponibilidade e gerenciamento de Pool de Front-Ends
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Saiba mais sobre o gerenciamento de pool de front-end no Skype for Business Server, incluindo o gerenciamento de pools, a perda de quorum e etapas especiais para pools com apenas dois servidores front-end.
ms.openlocfilehash: 731284d6df761b7fb023c92c656cae5cd6d0ed77
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815909"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidade e gerenciamento de Pool de Front-Ends
 
Saiba mais sobre o gerenciamento de pool de front-end no Skype for Business Server, incluindo o gerenciamento de pools, a perda de quorum e etapas especiais para pools com apenas dois servidores front-end.
  
No Skype for Business Server, a arquitetura dos pools front-ends usa um modelo de sistema distribuído, com os dados de cada usuário mantidos em até três servidores front-end no pool. Recomendamos que todos os seus pools do front-end da Enterprise Edition incluam pelo menos três servidores front end. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planejando o gerenciamento de Pool de Front-Ends

 O Skype for Business Server usa um modelo de sistema distribuído baseado no Windows Fabric. Nesse modelo, os dados importantes para cada usuário e conferência são armazenados em três servidores front-end em um pool de front-ends. Esses três servidores que armazenam um determinado conjunto de dados são calledreplicas.
  
Com o modelo distribuído para grupos de front-end, um determinado número de servidores de um pool deve estar em execução para que o pool funcione. Há dois modos de perda para um pool.
  
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
|254  <br/> |8  <br/> |
|11:00  <br/> |9  <br/> |
|12  <br/> |254  <br/> |
|16 **para o Skype for Business Server 2019** <br/> |12  <br/> |


   
Cada vez subsequente que o pool for iniciado, 85% dos servidores devem ser iniciados (conforme exibido na tabela anterior). Se esse número de servidores não puder ser iniciado (mas servidores suficientes puderem ser iniciados para que você não tenha perda de quorum no nível do pool), `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` você pode usar o cmdlet para permitir que o pool se recupere dessa perda de quorum em nível de grupo de roteamento e faça o progresso. Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> Em pools com um número par de servidores, o Skype for Business Server usa o banco de dados SQL primário como testemunha. Em um pool como esse, se você desligar o banco de dados primário, alternar para a cópia Espelho e desligar alguns servidores Front-End, de modo que o número de servidores em execução seja insuficiente, de acordo com a tabela anterior, todo o pool será desligado. Para obter mais informações, consulte [testemunha de espelhamento de banco de dados](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perda de quórum no nível do pool

Para que um pool de front-end funcione, ele não pode estar em perda de quorum no nível do pool. Se o número de servidores em execução estiver abaixo do nível funcional conforme exibido na tabela anterior, os servidores restantes no pool interromperão todos os serviços do Skype for Business Server. Observe que os números na tabela a seguir pressupõem que os servidores back-end do pool estejam em execução.
  
|Número total de servidores front-end no pool  <br/> |Número de servidores que devem estar em execução para o pool ser funcional  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Qualquer um dos 2  <br/> |
|5-6  <br/> |Qualquer um dos 3  <br/> |
|7  <br/> |Qualquer um dos 4  <br/> |
|8-9  <br/> |Qualquer um dos 4 dos 7 primeiros servidores  <br/> |
|10-12  <br/> |Qualquer um dos 5 dos 9 primeiros servidores  <br/> |
|12-16 **para o Skype for Business Server 2019**  <br/> |Qualquer 7 dos primeiros 12 servidores  <br/> |
   
Na tabela anterior, os "primeiros servidores" são os servidores que foram exibidos primeiro, cronologicamente, quando o pool foi iniciado pela primeira vez. Para determinar esses servidores, você pode usar o `Get-CsComputer` cmdlet com a `-PoolFqdn` opção. Esse cmdlet exibirá os servidores na ordem em que aparecem na topologia, e aqueles que aparecem no topo da lista são os primeiros servidores.
  
> [!IMPORTANT]
> O número máximo de servidores front-end aumentou para 16 no [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Etapas adicionais para garantir que os pools sejam funcionais

Observe alguns outros fatores para garantir que seus Pools de Front-Ends permaneçam funcionais.
  
- Quando você mover usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos servidores front-end estejam em execução.
    
- Se você estabelecer um relacionamento de emparelhamento entre este e um outro pool para fins de recuperação de desastres, após estabelecer esse relacionamento você deve garantir que o pool tenha três servidores Front-End em execução simultânea em algum momento para sincronizar adequadamente os dados com o pool de backup. Para obter mais informações sobre emparelhamento de pool e recursos de recuperação de desastre, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool de Front-Ends com dois servidores Front-End

Não recomendamos implantar um pool de front-end que contenha apenas dois servidores front-end. Esse pequeno pool não fornecerá uma solução robusta de alta disponibilidade como um pool maior faria e demandará um gerenciamento mais cuidadoso. Além disso, se o servidor back-end de um pool de dois servidores estiver inoperante, o próprio pool em si provavelmente também entraria em breve. Se você quiser implantar apenas um ou dois servidores que executam o Skype for Business Server, recomendamos implantá-los como servidores Standard Edition.
  
Se você já precisa implantar um pool com dois servidores front-end, siga estas diretrizes:
  
- Se um dos dois servidores front-ends ficar inativo, tente trazer o servidor com falha para o backup assim que possível. Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.
    
- Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:
    
  - A prática recomendada é reiniciar os dois servidores front-end ao mesmo tempo. 
    
  - Se os dois servidores não podem ser reiniciados ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.
    
  - Se não for possível recolocá-los nesse pedido, use o cmdlet a seguir antes de colocar o backup do pool:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Falhas e alterações na configuração do Pool de Front-Ends

Se um servidor Front-End falhar e não puder ser substituído em alguns dias ou mais, remova o servidor da topologia. Adicione o novo servidor Front-End à topologia quando estiver disponível novamente.
  
Sempre que fizer uma alteração na configuração de um Pool de Front-Ends, como adicionar ou remover servidores, você deve seguir estas diretrizes:
  
- Após a publicação da nova topologia, você deve reiniciar cada servidor Front-End no pool. Reinicie todos, um de cada vez.
    
- Se o pool inteiro estiver inoperante durante a alteração de configuração, execute o seguinte cmdlet após a publicação da nova topologia:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

