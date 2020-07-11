---
title: Alta disponibilidade e gerenciamento do pool de front-ends
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
description: Saiba mais sobre o gerenciamento de pool de front-ends no Skype for Business Server, incluindo gerenciamento de pools, perda de quorum e etapas especiais para pools com apenas dois servidores front-end.
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098429"
---
# <a name="front-end-pool-high-availability-and-management"></a>Alta disponibilidade e gerenciamento do pool de front-ends
 
Saiba mais sobre o gerenciamento de pool de front-ends no Skype for Business Server, incluindo gerenciamento de pools, perda de quorum e etapas especiais para pools com apenas dois servidores front-end.
  
No Skype for Business Server, a arquitetura dos pools de front-ends usa um modelo de sistemas distribuídos, com os dados de cada usuário mantidos em até três servidores front-end no pool. Recomendamos que todos os pools de front-ends Enterprise Edition incluam pelo menos três servidores front-end.

> [!NOTE]
> O Skype for Business Server 2019 não é compatível com os pools de front-ends Enterprise Edition com dois servidores front-end e não permitirá que a topologia seja publicada nesse cenário.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planejamento para o gerenciamento de pools de front-ends

 O Skype for Business Server usa um modelo de sistemas distribuídos baseado no Windows Fabric. Nesse modelo, os dados importantes de cada usuário e conferência são armazenados em três servidores front-end em um pool de front-ends. Esses três servidores que armazenam um determinado conjunto de dados são calledreplicas.
  
Com o modelo distribuído para pools de front-ends, um determinado número de servidores de um pool deve estar em execução para que o pool funcione. Há dois modos de perda para um pool.
  
- Perda de quorum de nível de grupo de roteamento, causada por servidores de réplica insuficientes para um grupo de roteamento específico. Um grupo de roteamento é um conjunto de usuários hospedados no pool. Cada grupo de roteamento tem três réplicas no pool: uma réplica primária e duas réplicas secundárias.
    
- Perda de quorum no nível do pool, causada quando não há servidores semente suficientes em execução no pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perda de quórum no nível do grupo de roteamento

Na primeira vez que você iniciar um novo pool de front-ends, é essencial que 85% dos servidores estejam em funcionamento, conforme mostrado na tabela a seguir. Se menos servidores estiverem em execução, os serviços poderão estar presos no estado inicial e o pool pode não iniciar.
  
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
|16 **para o Skype for Business Server 2019** <br/> |12   <br/> |


   
Cada vez subsequente que o pool é iniciado, 85% dos servidores devem ser iniciados (conforme mostrado na tabela anterior). Se este número de servidores não puder ser iniciado (mas servidores suficientes podem ser iniciados para que você não esteja em perda de quorum no nível do pool), você pode usar o `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet para permitir que o pool se recupere dessa perda de quorum de nível de grupo de roteamento e faça o andamento. Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> Em pools com um número par de servidores, o Skype for Business Server usa o banco de dados SQL principal como testemunha. Em um pool como este, se você desligar o banco de dados primário e alternar para a cópia espelho e desligar servidores de front-end suficientes para que o suficiente esteja sendo executado de acordo com a tabela anterior, todo o pool será desativado. Para obter mais informações, consulte [testemunha de espelhamento de banco de dados](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perda de quorum no nível do pool

Para que um pool de front-ends funcione, ele não pode ficar em perda de quorum no nível do pool. Se o número de servidores em execução estiver abaixo do nível funcional, conforme mostrado na tabela a seguir, os servidores restantes do pool interromperão todos os serviços do Skype for Business Server. Observe que os números na tabela a seguir pressupõem que os servidores de back-end no pool estão em execução.
  
|Número total de Servidores de Front End no pool  <br/> |Número de servidores que devem estar em execução para o pool ser funcional  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Qualquer 2  <br/> |
|5-6  <br/> |Qualquer 3  <br/> |
|7   <br/> |Qualquer 4  <br/> |
|8-9  <br/> |Quatro dos primeiros sete servidores  <br/> |
|10-12  <br/> |Qualquer 5 dos primeiros 9 servidores  <br/> |
|12-16 **para o Skype for Business Server 2019**  <br/> |Qualquer 7 dos primeiros 12 servidores  <br/> |
   
Na tabela anterior, os "primeiros servidores" são os servidores que foram inicialmente exibidos, cronologicamente, quando o pool foi iniciado pela primeira vez. Para determinar esses servidores, você pode usar o `Get-CsComputer` cmdlet com a `-PoolFqdn` opção. Este cmdlet mostrará os servidores na ordem em que eles aparecem na topologia e aqueles que estão na parte superior da lista são os primeiros servidores.
  
> [!IMPORTANT]
> O número máximo de servidores front-end aumentou para 16 no [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Etapas adicionais para garantir que os pools sejam funcionais

Você deve observar alguns outros fatores para garantir que seus pools de front-ends permaneçam funcionais.
  
- Ao migrar usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos Servidores de Front End estão em execução.
    
- Se você estabelecer uma relação de emparelhamento entre este pool e outro pool para fins de recuperação de desastres, depois de estabelecer essa relação, você deve ter certeza de que esse pool tenha três servidores front-end sendo executados simultaneamente em algum momento para sincronizar corretamente os dados com o pool de backup. Para obter mais informações sobre emparelhamento de pool e recursos de recuperação de desastre, consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool de front-ends com dois servidores front-end

Não recomendamos implantar um pool de Front Ends que contém apenas dois Servidores de Front End. Este pequeno pool não fornecerá uma solução robusta de alta disponibilidade, como um pool maior, e precisará de cuidado adicional no gerenciamento. Além disso, se o servidor back-end de um pool de dois servidores for desativado, o próprio pool inteiro provavelmente também será desativado em breve. Se quiser implantar apenas um ou dois servidores que executam o Skype for Business Server, recomendamos que você os implante como servidores Standard Edition.
  
Se você precisar implantar um pool com dois servidores front-end, siga estas diretrizes:
  
- If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.
    
- Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:
    
  - A prática recomendada é reiniciar ambos os servidores front-end ao mesmo tempo. 
    
  - Se os dois servidores não podem ser reinicidos ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.
    
  - Se você não puder trazê-los novamente nessa ordem, use o seguinte cmdlet antes de colocar o pool de backup:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Falhas e alterações na configuração do pool de front-ends

Se um servidor front-end falhar e for improvável de ser substituído por alguns dias ou mais, remova o servidor da topologia. Adicione o novo servidor front-end à topologia quando ele estiver disponível novamente.
  
Sempre que você fizer uma alteração na configuração para um pool de front-ends, como adicionar ou remover servidores, deverá seguir estas diretrizes:
  
- Após a publicação da nova topologia, você deve reiniciar cada servidor de front-end no pool. Reinicie todos eles, um de cada vez.
    
- Se o pool inteiro tiver sido desativado durante a alteração da configuração, execute o seguinte cmdlet após a publicação da nova topologia:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

