---
title: Planejamento de atualização para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Resumo: Saiba mais sobre as coisas que você deve considerar ao planejar uma atualização para o Skype for Business Server 2015. Baixe um teste grátis do Skype for Business Server 2015 a partir do centro de avaliação da https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft em:.'
ms.openlocfilehash: a812d0fac6d6d9e181f9216c73070c0bf085f368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815569"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planejamento de atualização para o Skype for Business Server 2015
 
Resumo: Saiba mais sobre as coisas que você deve considerar ao planejar uma atualização para o Skype for Business Server 2015. Baixe um teste grátis do Skype for Business Server 2015 a partir do centro de avaliação da [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft em:.
  
Como parte do seu plano de atualização para o Skype for Business Server 2015, use este tópico para compreender os caminhos de atualização recomendados para o Skype for Business Server 2015, como funciona a atualização in-loco, quais são os cenários de coexistência com suporte e o processo de atualização se parecer.

> [!NOTE]
> As atualizações in-loco estavam disponíveis no Skype for Business Server 2015, mas não são mais compatíveis com o Skype for Business Server 2019. A coexistência de lado a lado tem suporte, confira [migrar para o Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Caminhos de atualização recomendados para o Skype for Business Server 2015

 Para atualizar do Lync Server 2013, Lync Server 2010 ou Office Communications Server 2007 R2 para o Skype for Business Server 2015, use os seguintes caminhos de atualização:
  
> [!CAUTION]
> A Atualização In-loco move automaticamente os diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015. No entanto, se você planeja mover manualmente os diretórios de conferência, é muito importante usar o Shell de Gerenciamento do Skype for Business Server 2015. Se você tentar usar o Shell de Gerenciamento do Lync Server 2013 para mover os diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015, poderá ocorrer perda de dados. Em geral, sempre que você estiver trabalhando com o Skype for Business Server 2015 em qualquer capacidade, deverá usar sempre o conjunto de ferramentas do Skype for Business Server 2015.  
  
|**Versão**|**Recomendações**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para atualizar, use o construtor de topologia do Skype for Business Server e o novo recurso de atualização in-loco em cada um dos servidores associados ao pool. consulte [planejar a atualização do Lync server 2013 para o Skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) e [atualizar para o Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) para obter etapas detalhadas. <br/> |
|Skype for Business Server 2010 + Skype for Business Server 2013 (modo duplo)  <br/> |Primeiro, atualize para o Lync Server 2013 e, em seguida, atualize para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco. No entanto, se a topologia primária for do Lync Server 2010, também é possível reverter os componentes do Lync Server 2013 para o Lync Server 2010 e, em seguida, atualizar diretamente para o Skype for Business Server 2015. Nesse caso, você pode aproveitar o recurso de atualização in-loco e usa a simples coexistência entre o Lync Server 2010 e o Skype for Business Server 2015. Não há suporte para a coexistência tripla, mas para a coexistência sim.  <br/> |
|Lync Server 2010  <br/> |Crie um pool novo do Skype for Business Server 2015 e migre os usuários para esse novo pool. Você poderá encerrar o antigo pool do Skype for Business Server 2010. A atualização do Lync Server 2010 para o Skype for Business Server 2015 é semelhante à atualização do Lync Server 2010 para o Lync Server 2013. Consulte [migração do Lync server 2010 para o Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Escolha uma das duas opções: <br/>  Configurar um novo ambiente do Skype for Business Server 2015. <br/>  Ou se seu hardware e software atendem aos requisitos do Skype for Business Server 2015, atualize para o Lync Server 2013 e, em seguida, atualize para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco. Para obter mais informações, consulte [requisitos do servidor para o Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) e [migração do Office communications Server 2007 R2 para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> O SQL Server 2014 tem suporte no Skype for Business Server 2015, mas não é compatível com o Lync Server 2013. Se você deseja atualizar do SQL Server 2012 para o SQL Server 2014, primeiro o pool deve ser atualizado para o Skype for Business Server 2015 usando o método de atualização in-loco, conforme descrito neste documento. Em seguida, você pode atualizar do SQL Server 2012 para o SQL Server 2014, confira [atualizar para o SQL server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Para saber mais sobre os requisitos de banco de dados, confira [requisitos de servidor para o Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planejar atualização do Lync Server 2013 para o Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode atualizar os sistemas do Lync Server 2013 para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco. A atualização in-loco oferece uma solução com um único clique que faz o backup de certificados, desinstale componentes do servidor, atualize bancos de dados locais e instale as funções do Skype for Business Server 2015. A atualização in-loco busca manter o hardware e os investimentos em servidor existentes, reduzindo o custo geral para implantar o Skype for Business Server 2015.
  
> [!NOTE]
> A atualização in-loco permite que você use o mesmo hardware ao atualizar para o Skype for Business Server. No entanto, reutilizar o mesmo hardware não significa obter a mesma capacidade de desempenho. Você não deve esperar que as cargas de desempenho do Lync Server 2013 e do Skype for Business Server 2015 sejam idênticas. 
  
> [!NOTE]
> A atualização in-loco não é compatível com alta disponibilidade ou recuperação de desastres para o Skype for Business Server. 
  
A atualização in-loco envolve a colocação do pool do Lync Server 2013 offline e a atualização do pool do Skype for Business Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Criar um plano de atualização in-loco

Certifique-se de que o plano defina:
  
1. Uma compreensão da sua topologia atual.
    
    > [!NOTE]
    > Não se esqueça de desinstalar a ferramenta de administração do LRS para o Lync Server 2013 antes de executar a atualização in-loco. A ferramenta de administração do LRS para o Lync Server 2013 não pode coexistir com o Skype for Business Server 2015. Depois de executar a atualização in-loco, instale a nova ferramenta de administração do LRS. Consulte [portal da Web administrativo do sistema de sala do Microsoft Lync para o Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) para obter mais detalhes.
  
2. O pool primário da atualização.
    
3. Se você vai atualizar os bancos de dados de Monitoramento e Arquivamento, ou se criará novos bancos de dados.
    
4. Os métodos de atualização in-loco poderão ser Offline ou Mover usuários. Como parte da opção Mover usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. 
    
5. Um plano de comunicação para os usuários afetados.
    
6. Um plano de backup em caso de falha na atualização.
    
Qualquer usuário que estiver no pool principal enquanto ele está sendo atualizado não conseguirá usar os serviços até que a atualização seja concluída. Se você tiver um pool secundário em funcionamento, pode evitar que seus usuários sejam afetados movendo-os para esse pool antes da atualização. Após a atualização, mova os usuários de volta para o pool primário.
  
### <a name="in-place-upgrade-methods"></a>Métodos de atualização in-loco

Há dois cenários para a atualização in-loco: 
  
- O método Mover Usuário, que não requer tempo de inatividade para os usuários. 
    
- O método Offline, que requer tempo de inatividade.
    
Recomendamos que uma atualização com o método Offline seja agendada durante uma janela de manutenção e que os usuários sejam notificados sobre o tempo de inatividade.
  
> [!NOTE]
> Quando estiver atualizando um pool pareado no Lync Server 2013 e quiser atualizar os dois pools para Skype for Business Server 2015, atualize o segundo pool imediatamente após a atualização do primeiro pool. Quando um pool estiver executando o Lync Server 2013 e o segundo pool estiver executando o Skype for Business Server 2015, as opções de recuperação de desastres são minimizadas. Por exemplo, se um pool estiver executando 2013 e o segundo estiver executando o 2015 e ocorrer um desastre, é possível que você tenha perda de dados, pois a recuperação de falhas do pool não é suportada no modo desastre quando pools emparelhados não estiverem na mesma versão. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método Offline de atualização in-loco

Use este método se você não quiser mover usuários entre pools de usuários. Durante a atualização, os usuários não poderão usar o Lync ou o Skype for Business Services. 
  
O diagrama a seguir mostra uma visão geral deste processo.
  
![Lync 2013 para usuários do Skype offline](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Se você tiver pools pareados, não separe-os antes da atualização. 
  
Quando a atualização de um pool de servidores for iniciada, o pool inteiro deve ser atualizado. O Skype for Business Server não oferece suporte à atualização de apenas parte do pool. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Mover Usuários (sem tempo de inatividade para o usuário)
<a name="bkmk_MoveUsersMethod"> </a>

Para usar esse método, mova os usuários para outro pool antes de iniciar a atualização. Durante a atualização, os usuários podem usar os serviços do Lync. Depois que eles forem movidos para o pool atualizado, poderão usar o Skype for Business. O seguinte diagrama mostra uma visão geral desse processo.
  
> [!IMPORTANT]
> Como parte da opção Mover usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. A Conferência Discada PSTN ainda irá resolver a ID de Conferência para o pool que será atualizado, em vez do pool pareado. Então, você terá que mover os Diretórios de conferência se quiser que conferências PSTN agendadas no pool sejam acessíveis durante a atualização. 
  
![Diagrama de nada que mostra os usuários sendo movidos para outro pool antes que o pool seja atualizado e movido de volta para o pool após a atualização.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover usuários para atualização de hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Se o seu hardware não atender aos [requisitos do servidor do Skype for Business server 2015](requirements-for-your-environment/server-requirements.md), configure um novo ambiente do Skype for business Server 2015 e mova os usuários para lá. O seguinte diagrama mostra uma visão geral do processo para atualizar a partir do Lync Server 2010. 
  
![Diagrama de pista de nada que mostra os usuários no pool de front-end primário do Lync Server sendo movidos para o Skype for Business Server 2015 e o pool do servidor do Lync sendo descomissionado.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processo de atualização in-loco

 Atualize do Lync Server 2013 para o Skype for Business Server 2015 usando as seguintes etapas:
  
1. Faça backup de todos os bancos de dados antes da atualização.
    
2. Verifique se todos os serviços que serão atualizados estão em estado de execução.
    
3. Atualize e publique o arquivo de topologia usando o Construtor de Topologias.
    
4. Interrompa todos os serviços em todos os Servidores Front-End.
    
5. Instale novos pré-requisitos necessários para o Skype for Business Server.
    
6. Inicie a atualização in-loco em cada Servidor Front-End.
    
7. Quando a atualização tiver sido concluída, reinicie todos os serviços.
    
   - Para o Pool de Front-Ends, reinicie os serviços usando o comando Start-CsPool.
    
   - Para Servidor não-Front-End, use o comando Start-CSWindowsService.
    
> [!NOTE]
>  Se você não quiser atualizar seus bancos de dados existentes de Monitoramento e Arquivamento, remova a dependência antes de atualizar a topologia. Se quiser criar novos bancos de dados existentes de Monitoramento e Arquivamento durante a atualização, você pode criar um novo repositório do SQL e associá-lo ao pool. Você pode encontrar as etapas sobre como fazer isso no tópico[atualizar para o Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > atualização in-loco não é compatível com alta disponibilidade ou recuperação de desastres para o Skype for Business Server. Para evitar a interrupção dos serviços dos usuários, use o [método mover usuários (sem tempo de inatividade do usuário)](upgrade.md#bkmk_MoveUsersMethod) para atualizar. > durante o processo de atualização, a réplica XDS é colocada na pasta compartilhada local na unidade de disco com mais espaço livre. Se o disco for removido posteriormente, você pode ter problemas, como os serviços não iniciarem.
  
### <a name="upgrade-order"></a>Ordem de atualização

Atualize a topologia de dentro para fora. Atualize primeiro todos os seus pools, depois os servidores de borda e por fim o pool do Repositório de Gerenciamento Central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Considerações sobre a autenticação Kerberos

Se você usar a autenticação Kerberos para serviços Web, deve atribuir novamente as contas Kerberos e redefinir a senha depois que a atualização in-loco tiver sido concluída. Para saber como fazer isso, confira [Configurando a autenticação Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Suporte para coexistência com o Lync Server 2013 e o Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode executar o Skype for Business Server 2015 na mesma topologia do Lync Server 2013 ou do Lync Server 2010, mas não pode ter os três na mesma topologia.
  
Se o Lync Server 2010 e o Lync Server 2013 coexistirem, será recomendável atualizar a topologia inteira para o Lync Server 2013 e depois atualizar para o Skype for Business Server 2015 usando a atualização in-loco. Para obter mais informações, consulte [migração do Lync server 2010 para o Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Se a sua topologia é primariamente do Lync Server 2010, reverta os componentes do Lync Server 2013 para o Lync Server 2010 antes de atualizar a topologia para o Skype for Business Server 2015. Nesse caso, você perde o benefício da atualização in-loco e tem uma topologia de coexistência entre o Lync Server 2010 e o Skype for Business Server 2015.
  
O diagrama a seguir mostra o suporte de coexistência do Skype for Business Server 2015 com o Lync Server 2013 e o Lync Server 2010.
  
![Um diagrama mostrando o suporte de coexistência do Skype for Business Server 2015 com o Lync Server 2013 ou o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processo de atualização com Aparelho de Filial Persistente e Servidor
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

O Skype for Business Server 2015 não oferece suporte a uma atualização local de um aplicativo de ramificação sobreviventes (SBA) ou a um servidor de ramificação sobreviventes (SBS).
  
No entanto, damos suporte à coexistência de datacenters do Skype for Business Server com o SBA/SBS do Lync Server 2010 ou do Lync Server 2013. 
  
Ao planejar uma atualização in-loco de um Pool de Front-Ends (FE) do Lync Server 2013 com uma filial associada, você pode deixar os usuários existentes do SBA/SBS do Lync Server 2013. Durante a atualização, os usuários do SBA/SBS entrarão em modo de resiliência e voltarão ao funcionamento normal após a conclusão da atualização. Para obter mais informações sobre a experiência dos usuários durante o modo de resiliência, consulte [recursos de resiliência de site de ramificação no Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Ao fazer a migração de uma topologia do Lync Server 2010 para o Skype for Business Server 2015, o SBA/SBS deve ser adicionado novamente à topologia, de modo semelhante à migração para o Lync Server 2013. Para ver as etapas necessárias, leia [conectando aparelho de ramificação sobreviventes ao pool de front-end do Lync Server 2013](https://technet.microsoft.com/library/jj688026.aspx).
  
Para topologias de coexistência do Lync Server 2010 e do Lync Server 2013, alinhe primeiro às recomendações feitas na seção ' suporte para coexistência com o Lync Server 2013 e o Lync Server 2010 '.
  
## <a name="see-also"></a>Confira também
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Atualização para o Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
