---
title: Planejamento de atualização para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Resumo: Saiba sobre as coisas que você deve considerar ao planejar uma atualização para o Skype Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 711b675c902824e6aab31ed64266a946a135b7fb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899162"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planejamento de atualização para o Skype for Business Server 2015
 
Resumo: Saiba sobre as coisas que você deve considerar ao planejar uma atualização para o Skype Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Como parte do seu plano para atualizar para o Skype para Business Server 2015, use este tópico para entender os caminhos de atualização recomendados para Skype para negócios 2015 do servidor, como a atualização In-loco funciona, quais são os cenários de coexistência suportados e que o processo de atualização a aparência.

> [!NOTE]
> Atualizações in-loco estavam disponíveis no Skype para Business Server 2015, mas não são mais suportadas no Skype para Business Server 2019. Lado a lado coexistência é suportada, consulte [Migration to Skype para Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Caminhos de atualização recomendados para Skype para Business Server 2015

 Para atualizar do Lync Server 2013, Lync Server 2010 ou Office Communications Server 2007 R2 para Skype para Business Server 2015, use os seguintes caminhos de atualização:
  
> [!CAUTION]
> A Atualização In-loco move automaticamente os diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015. No entanto, se você planeja mover manualmente os diretórios de conferência, é muito importante usar o Shell de Gerenciamento do Skype for Business Server 2015. Se você tentar usar o Shell de Gerenciamento do Lync Server 2013 para mover os diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015, poderá ocorrer perda de dados. Em geral, sempre que você estiver trabalhando com o Skype for Business Server 2015 em qualquer capacidade, deverá usar sempre o conjunto de ferramentas do Skype for Business Server 2015.  
  
|**Versão**|**Recomendações**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para atualizar, use o Skype para negócios construtor de topologia de servidor e o novo recurso de atualização in-loco em cada um dos servidores associados ao pool. Para obter etapas detalhadas, consulte [Planejar a atualização do Lync Server 2013 para Skype para Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) e [atualizar para o Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Skype for Business Server 2010 + Skype for Business Server 2013 (modo duplo)  <br/> |Primeiro, atualizar para o Lync Server 2013 e depois atualize para Skype para Business Server 2015 usando o novo recurso de atualização in-loco. No entanto, se a topologia primária for do Lync Server 2010, também é possível reverter os componentes do Lync Server 2013 para o Lync Server 2010 e, em seguida, atualizar diretamente para o Skype for Business Server 2015. Nesse caso, você pode aproveitar o recurso de atualização in-loco e usa a simples coexistência entre o Lync Server 2010 e o Skype for Business Server 2015. Não há suporte para a coexistência tripla, mas para a coexistência sim.  <br/> |
|Lync Server 2010  <br/> |Crie um pool novo do Skype for Business Server 2015 e migre os usuários para esse novo pool. Você poderá encerrar o antigo pool do Skype for Business Server 2010. A atualização do Lync Server 2010 para o Skype for Business Server 2015 é semelhante à atualização do Lync Server 2010 para o Lync Server 2013. Consulte [migração do Lync Server 2010 para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Escolha uma das duas opções: <br/>  Configure um novo Skype para ambiente de negócios Server 2015. <br/>  Ou, se o seu hardware e software atendem aos requisitos de Skype para Business Server 2015, atualizar para o Lync Server 2013 e depois atualize para Skype para Business Server 2015 usando o novo recurso de atualização in-loco. Para obter mais informações, consulte [requisitos de servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md) e [migração do Office Communications Server 2007 R2 para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 é suportado no Skype para Business Server 2015, mas não é suportado no Lync Server 2013. Se você deseja atualizar do SQL Server 2012 para o SQL Server de 2014, em seguida, o pool deve ser atualizado primeiro para Skype para negócios 2015 de servidor usando o método de atualização In-loco, conforme descrito neste documento. Em seguida, você pode atualizar do SQL Server 2012 para o SQL Server de 2014, consulte [atualizar para o SQL Server de 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Para saber mais sobre os requisitos de banco de dados, consulte [requisitos de servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planejar atualização do Lync Server 2013 para o Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode atualizar sistemas do Lync Server 2013 para Skype para negócios 2015 de servidor usando o novo recurso de atualização in-loco. Atualização in-loco fornece uma solução de um clique que faz o backup de certificados, desinstala os componentes de servidor, atualiza os bancos de dados locais e instala o Skype para funções de negócios Server 2015. Atualização in-loco procura preservar o hardware existente e investimentos de servidor, reduzindo o custo total para implantar o Skype para Business Server 2015.
  
> [!NOTE]
> Atualização in-loco permite que você use o mesmo hardware ao atualizar para o Skype para Business Server. No entanto, reutilizar o mesmo hardware não significa obter a mesma capacidade de desempenho. Você não deve esperar que as cargas de desempenho para o Lync Server 2013 e Skype para Business Server 2015 seja idêntico. 
  
> [!NOTE]
> Atualização in-loco não suporta alta disponibilidade ou recuperação de desastres para Skype para Business Server. 
  
Atualização in-loco envolve colocar o pool do Lync Server 2013 offline e atualizá-lo para uma Skype para Business Server 2015 pool. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Criar um plano de atualização in-loco

Certifique-se de que o plano defina:
  
1. Uma compreensão da topologia atual.
    
    > [!NOTE]
    > Certifique-se desinstalar a ferramenta de administração de LRS do Lync Server 2013 antes de executar a atualização in-loco. A ferramenta de administração do Lync Server 2013 LRS não podem coexistir com Skype para Business Server 2015. Após executar a atualização in-loco instalar a nova ferramenta de administração de LRS, consulte [Microsoft Lync sala sistema administrativas Portal da Web para Skype para Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. O pool primário para a atualização.
    
3. Se você vai atualizar os bancos de dados de Monitoramento e Arquivamento, ou se criará novos bancos de dados.
    
4. Os métodos de atualização in-loco poderão ser Offline ou Mover usuários. Como parte da opção Mover usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. 
    
5. Um plano de comunicação para os usuários afetados.
    
6. Um plano de backup em caso de falha na atualização.
    
Qualquer usuário que estiver no pool principal enquanto ele está sendo atualizado não conseguirá usar os serviços até que a atualização seja concluída. Se você tiver um pool secundário em funcionamento, pode evitar que seus usuários sejam afetados movendo-os para esse pool antes da atualização. Após a atualização, mova os usuários de volta ao pool primário.
  
### <a name="in-place-upgrade-methods"></a>Métodos de atualização in-loco

Há dois cenários para a atualização in-loco: 
  
- O método Mover Usuário, que não requer tempo de inatividade para os usuários. 
    
- O método Offline, que requer tempo de inatividade.
    
Recomendamos que uma atualização com o método Offline seja agendada durante uma janela de manutenção e que os usuários sejam notificados sobre o tempo de inatividade.
  
> [!NOTE]
> Quando estiver atualizando um pool pareado no Lync Server 2013 e quiser atualizar os dois pools para Skype for Business Server 2015, atualize o segundo pool imediatamente após a atualização do primeiro pool. Quando um pool estiver executando o Lync Server 2013 e o segundo pool estiver executando o Skype for Business Server 2015, as opções de recuperação de desastres são minimizadas. Por exemplo, se um pool estiver executando 2013 e o segundo estiver executando o 2015 e ocorrer um desastre, é possível que você tenha perda de dados, pois a recuperação de falhas do pool não é suportada no modo desastre quando pools emparelhados não estiverem na mesma versão. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método Offline de atualização in-loco

Use este método se você não quiser mover usuários entre pools de usuários. Durante a atualização, os usuários não poderão usar o Lync ou Skype para serviços corporativos. 
  
O diagrama a seguir mostra uma visão geral deste processo.
  
![Lync 2013 para usuários do Skype Offline](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Se você tiver pools pareados, não separe-os antes da atualização. 
  
Quando a atualização de um pool de servidores for iniciada, o pool inteiro deve ser atualizado. Skype para Business Server não oferece suporte a ter apenas uma parte do pool atualizado. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Mover Usuários (sem tempo de inatividade para o usuário)
<a name="bkmk_MoveUsersMethod"> </a>

Para usar esse método, mova os usuários para outro pool antes de iniciar a atualização. Durante a atualização, os usuários podem usar os serviços do Lync. Depois que elas serão movidas para o pool atualizado, eles podem usar Skype para negócios. O seguinte diagrama mostra uma visão geral desse processo.
  
> [!IMPORTANT]
> Como parte da opção Mover usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. A Conferência Discada PSTN ainda irá resolver a ID de Conferência para o pool que será atualizado, em vez do pool pareado. Então, você terá que mover os Diretórios de conferência se quiser que conferências PSTN agendadas no pool sejam acessíveis durante a atualização. 
  
![Diagrama swim que mostra aos usuários sendo movidos para outro pool antes do pool é atualizado e sendo movido de volta para o pool depois que ele é atualizado.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover usuários para atualização de hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Se o seu hardware não cumprir os [requisitos de servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md), configure um novo Skype para ambiente de negócios Server 2015 e mover usuários lá. O seguinte diagrama mostra uma visão geral do processo para atualizar a partir do Lync Server 2010. 
  
![Nadar diagrama raias que mostra aos usuários do pool de Front-End principal do Lync Server sendo transferido para Skype para Business Server 2015 e o pool do Lync Server está sendo encerrado.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processo de atualização in-loco

 Atualização do Lync Server 2013 Skype para 2015 do servidor de negócios usando as seguintes etapas:
  
1. Faça backup de todos os bancos de dados antes da atualização.
    
2. Verifique se todos os serviços que serão atualizados estão em estado de execução.
    
3. Atualize e publique o arquivo de topologia usando o Construtor de Topologias.
    
4. Interrompa todos os serviços em todos os Servidores Front-End.
    
5. Instale novos pré-requisitos necessários para Skype para Business Server.
    
6. Inicie a atualização in-loco em cada Servidor Front-End.
    
7. Quando a atualização tiver sido concluída, reinicie todos os serviços.
    
   - Para o Pool de Front-Ends, reinicie os serviços usando o comando Start-CsPool.
    
   - Para Servidor não-Front-End, use o comando Start-CSWindowsService.
    
> [!NOTE]
>  Se você não quiser atualizar seus bancos de dados existentes de Monitoramento e Arquivamento, remova a dependência antes de atualizar a topologia. Se quiser criar novos bancos de dados existentes de Monitoramento e Arquivamento durante a atualização, você pode criar um novo repositório do SQL e associá-lo ao pool. Você pode encontrar as etapas sobre como fazer isso, no tópico,[atualizar para o Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). atualização in-loco de gt _ não suporta alta disponibilidade ou recuperação de desastres para Skype para Business Server. Para evitar interromper os serviços dos usuários, use o [método Move Users (sem tempo de inatividade do usuário)](upgrade.md#bkmk_MoveUsersMethod) para upgrade.> durante o processo de atualização que a réplica de xds é colocada na pasta compartilhada local na unidade de disco com mais espaço livre. Se o disco for removido posteriormente, você pode ter problemas, como os serviços não iniciarem.
  
### <a name="upgrade-order"></a>Ordem de atualização

Atualize a topologia de dentro para fora dele. Atualize primeiro todos os seus pools, depois os servidores de borda e por fim o pool do Repositório de Gerenciamento Central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Considerações sobre a autenticação Kerberos

Se você usar a autenticação Kerberos para serviços Web, deve atribuir novamente as contas Kerberos e redefinir a senha depois que a atualização in-loco tiver sido concluída. Para saber como fazer isso, consulte [Configurando a autenticação Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Suporte para coexistência com o Lync Server 2013 e Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode executar o Skype for Business Server 2015 na mesma topologia do Lync Server 2013 ou do Lync Server 2010, mas não pode ter os três na mesma topologia.
  
Se o Lync Server 2010 e o Lync Server 2013 coexistirem, será recomendável atualizar a topologia inteira para o Lync Server 2013 e depois atualizar para o Skype for Business Server 2015 usando a atualização in-loco. Para obter mais informações, consulte [migração do Lync Server 2010 para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Se a sua topologia é primariamente do Lync Server 2010, reverta os componentes do Lync Server 2013 para o Lync Server 2010 antes de atualizar a topologia para o Skype for Business Server 2015. Nesse caso, você perde o benefício da atualização in-loco e tem uma topologia de coexistência entre o Lync Server 2010 e o Skype for Business Server 2015.
  
O diagrama a seguir mostra o suporte de coexistência do Skype para 2015 do servidor de negócios com o Lync Server 2013 e Lync Server 2010.
  
![Um diagrama que mostra o suporte a coexistência Skype para 2015 do servidor de negócios com o Lync Server 2013 ou o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processo de atualização com Aparelho de Filial Persistente e Servidor
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype para Business Server 2015 não tem suporte para uma atualização In-loco de um aparelho de filial persistente (SBA) ou um servidor de filial persistente (SBS).
  
No entanto, damos suporte à coexistência de datacenters do Skype for Business Server com o SBA/SBS do Lync Server 2010 ou do Lync Server 2013. 
  
Ao planejar uma atualização in-loco de um Pool de Front-Ends (FE) do Lync Server 2013 com uma filial associada, você pode deixar os usuários existentes do SBA/SBS do Lync Server 2013. Durante a atualização, os usuários do SBA/SBS entrarão em modo de resiliência e voltarão ao funcionamento normal após a conclusão da atualização. Para obter mais informações sobre a experiência dos usuários durante o modo de resiliência, consulte [os recursos de resiliência de site de filial no Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Ao fazer a migração de uma topologia do Lync Server 2010 para o Skype for Business Server 2015, o SBA/SBS deve ser adicionado novamente à topologia, de modo semelhante à migração para o Lync Server 2013. Para conhecer as etapas necessárias, leia [Conectando aparelho de filial persistente ao pool de Front End do Lync Server 2013](https://technet.microsoft.com/library/jj688026.aspx).
  
Para topologias de coexistência do Lync Server 2010 e Lync Server 2013, alinhe primeiro às recomendações feitas na seção 'Suporte para coexistência com o Lync Server 2013 e Lync Server 2010'.
  
## <a name="see-also"></a>Consulte Também
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
