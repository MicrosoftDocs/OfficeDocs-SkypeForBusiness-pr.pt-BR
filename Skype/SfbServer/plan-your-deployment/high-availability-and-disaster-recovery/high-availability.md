---
title: Alta disponibilidade e gerenciamento do Pool de Front-End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Saiba mais sobre o gerenciamento de pool de Front-End no Skype for Business Server, incluindo o gerenciamento de pools, perda de quórum e etapas especiais para pools com apenas dois Servidores front-end.
ms.openlocfilehash: 3f1924b7a8ad26b880f8674ada4f0c99a1bc4596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802791"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidade e gerenciamento do Pool de Front-End
 
Saiba mais sobre o gerenciamento de pool de Front-End no Skype for Business Server, incluindo o gerenciamento de pools, perda de quórum e etapas especiais para pools com apenas dois Servidores front-end.
  
No Skype for Business Server, a arquitetura dos pools de Front-End usa um modelo de sistemas distribuídos, com os dados de cada usuário mantidos em até três Servidores front-end no pool. Recomendamos que todos os seus pools de Front End Enterprise Edition incluam pelo menos três Servidores front-end.

> [!NOTE]
> O Skype for Business Server 2019 não dá suporte a pools de Front End Enterprise Edition com dois Servidores Front-End e não permitirá que a topologia seja publicada nesse cenário.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planejamento para o gerenciamento de pools de Front-End

 O Skype for Business Server usa um modelo de sistemas distribuídos baseado no Windows Fabric. Nesse modelo, dados importantes para cada usuário e conferência são armazenados em três Servidores front-end em um pool de Front-End. Esses três servidores que armazenaram um determinado conjunto de dados são chamados dereplicas.
  
Com o modelo distribuído para pools de Front-End, um determinado número de servidores de um pool deve estar em execução para que o pool funcione. Há dois modos de perda para um pool.
  
- Perda de quórum no Nível de Grupo de Roteamento, causada por servidores de réplica não suficientes para um grupo de roteamento específico. Um grupo de roteamento é um conjunto de usuários que estão no pool. Cada grupo de roteamento tem três réplicas no pool: uma réplica primária e duas réplicas secundárias.
    
- Perda de quórum no nível do pool, causada quando não há servidores de dados suficientes em execução no pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perda de quórum no nível do grupo de roteamento

Na primeira vez que você iniciar um novo pool de Front-End, é essencial que 85% dos servidores estão em execução, conforme mostrado na tabela a seguir. Se menos servidores estão sendo executados, os serviços podem ficar travados no estado inicial e o pool pode não iniciar.
  
|Número total de servidores no pool  <br/> |Número de servidores que devem estar em execução para que o pool seja iniciado pela primeira vez  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **Para o Skype for Business Server 2019** <br/> |12   <br/> |


   
Sempre que o pool for iniciado, 85% dos servidores devem ser iniciados (conforme mostrado na tabela anterior). Se esse número de servidores não puder ser iniciado (mas servidores suficientes puderem ser iniciados para que você não tenha perda de quórum no nível do pool), você poderá usar o cmdlet para permitir que o pool se recupere dessa perda de quórum no nível do grupo de roteamento e faça  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` progresso. Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> Em pools com um número de servidores, o Skype for Business Server usa o banco de dados SQL principal como testemunha. Em um pool como este, se você desligar o banco de dados primário e alternar para a cópia Espelho e desligar servidores front-end suficientes para que não sejam executados o suficiente de acordo com a tabela anterior, todo o pool será desligado. Para obter mais informações, consulte [Testemunha de espelhamento de banco de dados.](https://go.microsoft.com/fwlink/?LinkId=393672) 
  
#### <a name="pool-level-quorum-loss"></a>Perda de quórum no nível do pool

Para que um pool de Front-End funcione, ele não pode estar em perda de quórum no nível do pool. Se o número de servidores em execução ficar abaixo do nível funcional, conforme mostrado na tabela a seguir, os demais servidores no pool interromperão todos os serviços do Skype for Business Server. Observe que os números na tabela a seguir presumem que os Servidores back-end no pool estão em execução.
  
|Número total de Servidores de Front End no pool  <br/> |Número de servidores que devem estar em execução para o pool ser funcional  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Qualquer um dos 2  <br/> |
|5-6  <br/> |Qualquer um dos 3  <br/> |
|7   <br/> |Qualquer um dos 4  <br/> |
|8-9  <br/> |Qualquer um dos 4 dos 7 primeiros servidores  <br/> |
|10-12  <br/> |Qualquer um dos 5 dos 9 primeiros servidores  <br/> |
|12-16  **para o Skype for Business Server 2019**  <br/> |Qualquer um dos 7 dos primeiros 12 servidores  <br/> |
   
Na tabela anterior, os "primeiros servidores" são os servidores que foram trazidos primeiro, cronologicamente, quando o pool foi iniciado pela primeira vez. Para determinar esses servidores, você pode usar  `Get-CsComputer` o cmdlet com a `-PoolFqdn` opção. Este cmdlet mostrará os servidores na ordem em que aparecem na topologia, e os que estão na parte superior da lista são os primeiros servidores.
  
> [!IMPORTANT]
> O número máximo de servidores front-end aumentou para 16 [no Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Etapas adicionais para garantir que os pools sejam funcionais

Você deve observar alguns outros fatores para garantir que seus pools de Front End permaneçam funcionais.
  
- Ao migrar usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos Servidores de Front End estão em execução.
    
- Se você estabelecer uma relação de emparelhamento entre esse pool e outro pool para fins de recuperação de desastres, depois de estabelecer essa relação, você deve garantir que esse pool tenha três servidores front-end em execução simultânea em algum momento para sincronizar corretamente os dados com o pool de backup. Para obter mais informações sobre emparelhamento de pools e recursos de recuperação de desastres, consulte Plano para alta disponibilidade e recuperação de desastre [no Skype for Business Server.](high-availability-and-disaster-recovery.md) 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool de front-end com dois servidores front-end

Não recomendamos implantar um pool de Front Ends que contém apenas dois Servidores de Front End. Esse pequeno pool não fornecerá uma solução robusta de alta disponibilidade, como um pool maior, e precisa de mais cuidado no gerenciamento. Além disso, se o Servidor back-end de um pool de dois servidores cair, todo o pool em si provavelmente também cairá em breve. Se você quiser implantar apenas um ou dois servidores executando o Skype for Business Server, recomendamos implantá-los como servidores Standard Edition.
  
Se você precisar implantar um pool com dois Servidores Front-End, siga estas diretrizes:
  
- Se um dos dois Servidores de Front End ficar inativo, você deve ativá-lo assim que possível. Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.
    
- Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:
    
  - A prática melhor é reiniciar ambos os Servidores Front End ao mesmo tempo. 
    
  - Se os dois servidores não podem ser reinicidos ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.
    
  - Se não for possível auntá-los novamente nessa ordem, use o seguinte cmdlet antes de trazer o pool de volta:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Falhas e alterações na configuração do pool de Front End

Se um servidor front-end falhar e for improvável de ser substituído por alguns dias ou mais, remova o servidor da topologia. Adicione o novo servidor front-end à topologia quando ele estiver disponível novamente.
  
Sempre que você fizer uma alteração de configuração em um pool de Front-End, como adicionar ou remover servidores, siga estas diretrizes:
  
- Depois que a nova topologia tiver sido publicada, você deverá reiniciar cada servidor front-end no pool. Reinicie todos eles, um de cada vez.
    
- Se todo o pool tiver sido ino mesmo durante a alteração de configuração, execute o seguinte cmdlet após a publicação da nova topologia:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

