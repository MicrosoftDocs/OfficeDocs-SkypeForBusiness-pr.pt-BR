---
title: Alta disponibilidade e gerenciamento do Pool de Front End
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Saiba mais sobre o gerenciamento de pool de front-end no Skype for Business Server, incluindo o gerenciamento de pools, perda de quórum e etapas especiais para pools com apenas dois Servidores Front-End.
ms.openlocfilehash: cf1f5d4a65313ceabbc6cab279cd7889740c2f2c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417524"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidade e gerenciamento do Pool de Front End
 
Saiba mais sobre o gerenciamento de pool de front-end no Skype for Business Server, incluindo o gerenciamento de pools, perda de quórum e etapas especiais para pools com apenas dois Servidores Front-End.
  
No Skype for Business Server, a arquitetura dos pools de Front-End usa um modelo de sistemas distribuídos, com os dados de cada usuário mantidos em até três Servidores Front-End no pool. Recomendamos que todos os seus Edição Enterprise de front-end incluam pelo menos três Servidores Front-End.

> [!NOTE]
> Skype for Business Server 2019 não dá suporte Edição Enterprise pools de Front-End com dois Servidores Front-End e não permitirá que a topologia seja publicada nesse cenário.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planejamento para o gerenciamento de pools de Front-End

 Skype for Business Server usa um modelo de sistemas distribuídos com base em Windows Fabric. Neste modelo, os dados importantes para cada usuário e conferência são armazenados em três Servidores Front-End em um pool de Front-End. Esses três servidores que armazenaram um determinado conjunto de dados são chamados dereplicas.
  
Com o modelo distribuído para pools de Front-End, um determinado número de servidores de um pool deve estar sendo executado para que o pool funcione. Há dois modos de perda para um pool.
  
- Perda de quórum de Nível de Grupo de Roteamento, causada por servidores de réplica não suficientes para um determinado grupo de roteamento. Um grupo de roteamento é um conjunto de usuários que estão no pool. Cada grupo de roteamento tem três réplicas no pool: uma réplica primária e duas réplicas secundárias.
    
- Perda de quórum de nível de pool, causada quando servidores de sementes não suficientes estão sendo executados no pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perda de quórum de nível de grupo de roteamento

Na primeira vez que você iniciar um novo pool de Front-End, é essencial que 85% dos servidores estão em execução, conforme mostrado na tabela a seguir. Se menos servidores estão sendo executados, os serviços podem ficar travados no estado inicial e o pool pode não começar.
  
|Número total de servidores no pool  <br/> |Número de servidores que devem ser executados para que o pool seja iniciado pela primeira vez  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6   <br/> |5  <br/> |
|7   <br/> |5  <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11  <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **Para Skype for Business Server 2019** <br/> |12   <br/> |


   
Sempre que o pool for iniciado, 85% dos servidores devem ser iniciados (conforme mostrado na tabela anterior). Se esse número de servidores não puder ser iniciado (mas servidores suficientes puderem ser iniciados para que você não tenha perda de quórum no nível do pool),  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` você poderá usar o cmdlet para permitir que o pool se recupere dessa perda de quórum de nível de grupo de roteamento e faça progresso. Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> Em pools com um número único de servidores, o Skype for Business Server usa o banco de dados de SQL principal como Testemunha. Em um pool como esse, se você desligar o banco de dados principal e alternar para a cópia espelho e desligar servidores Front-End suficientes para que não sejam suficientes em execução de acordo com a tabela anterior, todo o pool será desligado. Para obter mais informações, consulte [Testemunha de Espelhamento de Banco de Dados](/sql/database-engine/database-mirroring/database-mirroring-witness). 
  
#### <a name="pool-level-quorum-loss"></a>Perda de quórum no nível do pool

Para que um pool de Front-End funcione, ele não pode estar em perda de quórum no nível do pool. Se o número de servidores em execução ficar abaixo do nível funcional, conforme mostrado na tabela a seguir, os servidores restantes no pool interromperão todos os Skype for Business Server serviços. Observe que os números na tabela a seguir pressuem que os Servidores Back-End no pool estão sendo executados.
  
|Número total de Servidores de Front End no pool  <br/> |Número de servidores que devem estar em execução para o pool ser funcional  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Qualquer 2  <br/> |
|5-6  <br/> |Qualquer 3  <br/> |
|7   <br/> |Qualquer 4  <br/> |
|8-9  <br/> |Qualquer um dos 4 primeiros 7 servidores  <br/> |
|10-12  <br/> |Qualquer um dos 5 primeiros 9 servidores  <br/> |
|12 a 16 **para Skype for Business Server 2019**  <br/> |Qualquer um dos 7 primeiros 12 servidores  <br/> |
   
Na tabela anterior, os "primeiros servidores" são os servidores que foram trazidos primeiro, cronologicamente, quando o pool foi iniciado pela primeira vez. Para determinar esses servidores, você pode usar o  `Get-CsComputer` cmdlet com a `-PoolFqdn` opção. Este cmdlet mostrará os servidores na ordem em que aparecem na topologia, e os que estão na parte superior da lista são os primeiros servidores.
  
> [!IMPORTANT]
> O número máximo de servidores front-end foi aumentado para 16 no [Skype for Business Server 2019](../../../SfBServer2019/plan/user-model-2019.md)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Etapas adicionais para garantir que os pools sejam funcionais

Você deve observar alguns outros fatores para garantir que seus pools de Front-End permaneçam funcionais.
  
- Ao migrar usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos Servidores de Front End estão em execução.
    
- Se você estabelecer uma relação de emparelhamento entre esse pool e outro pool para fins de recuperação de desastres, depois de estabelecer essa relação, certifique-se de que esse pool tenha três servidores Front-End em execução simultaneamente em algum momento para sincronizar corretamente os dados com o pool de backup. Para obter mais informações sobre os recursos de emparelhamento de pool e recuperação de desastres, consulte [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool de Front-End com dois servidores Front-End

Não recomendamos implantar um pool de Front Ends que contém apenas dois Servidores de Front End. Esse pool pequeno não fornecerá uma solução robusta de alta disponibilidade, como faria um pool maior, e precisa de um cuidado extra no gerenciamento. Além disso, se o Servidor Back-End de um pool de dois servidores tiver sido baixado, o pool inteiro provavelmente também será baixado em breve. Se você quiser implantar apenas um ou dois servidores executando Skype for Business Server, recomendamos implantá-los como servidores Edição Standard.
  
Se você precisar implantar um pool com dois Servidores Front-End, siga estas diretrizes:
  
- Se um dos dois Servidores de Front End ficar inativo, você deve ativá-lo assim que possível. Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.
    
- Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:
    
  - A prática prática é reiniciar ambos os Servidores Front-End ao mesmo tempo. 
    
  - Se os dois servidores não podem ser reinicidos ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.
    
  - Se você não puder trazê-los de volta nessa ordem, use o seguinte cmdlet antes de trazer o pool de volta:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Falhas e alterações na configuração do pool de front-end

Se um servidor Front-End falhar e for improvável que seja substituído por alguns dias ou mais, remova o servidor da topologia. Adicione o novo servidor Front-End à topologia quando ele estiver disponível novamente.
  
Sempre que você fizer uma alteração de configuração em um pool de Front-End, como adicionar ou remover servidores, siga estas diretrizes:
  
- Depois que a nova topologia tiver sido publicada, você deve reiniciar cada servidor Front-End no pool. Reinicie todos eles, um de cada vez.
    
- Se o pool inteiro tiver sido baixado durante a alteração de configuração, execute o seguinte cmdlet após a publicação da nova topologia:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
