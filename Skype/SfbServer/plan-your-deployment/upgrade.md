---
title: Planejar a atualização para o Skype for Business Server 2015
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
description: 'Resumo: Saiba mais sobre as coisas que você deve considerar ao planejar uma atualização para o Skype for Business Server 2015. Baixe uma avaliação gratuita do Skype for Business Server 2015 do centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 91cc78f22c03bf7ec59c9ac0c936f194ece71a35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030635"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planejar a atualização para o Skype for Business Server 2015
 
Resumo: Saiba mais sobre as coisas que você deve considerar ao planejar uma atualização para o Skype for Business Server 2015. Baixe uma avaliação gratuita do Skype for Business Server 2015 do centro de avaliação da Microsoft em [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
Como parte do seu plano para atualizar para o Skype for Business Server 2015, use este tópico para entender os caminhos de atualização recomendados para o Skype for Business Server 2015, como a atualização in-loco funciona, quais são os cenários de coexistência compatíveis e o processo de atualização é semelhante.

> [!NOTE]
> As atualizações in-loco estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. A coexistência de lado a lado é suportada, consulte [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Caminhos de atualização recomendados para o Skype for Business Server 2015

 Para atualizar do Lync Server 2013, Lync Server 2010 ou Office Communications Server 2007 R2 para o Skype for Business Server 2015, use os seguintes caminhos de atualização:
  
> [!CAUTION]
> A atualização in-loco move automaticamente os diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015. No entanto, se você planeja mover os diretórios de conferência manualmente, é muito importante usar o Shell de gerenciamento do Skype for Business Server 2015. Se você tentar usar o Shell de gerenciamento do Lync Server 2013 para mover os diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015, poderá ocorrer perda de dados. Em geral, sempre que você estiver trabalhando com o Skype for Business Server 2015 em qualquer capacidade, você deve usar o conjunto de ferramentas do Skype for Business Server 2015.  
  
|**Versão**|**Recomendações**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para atualizar, use o construtor de topologia do Skype for Business Server e o novo recurso de atualização in-loco em cada um dos servidores associados ao pool. consulte [plan to Upgrade from Lync server 2013 to Skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) e [upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) para obter etapas detalhadas. <br/> |
|Lync Server 2010 + Lync Server 2013 (modo duplo)  <br/> |Primeiro, atualize para o Lync Server 2013 e, em seguida, atualize para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco. No entanto, se sua topologia for principal do Lync Server 2010, você também poderá reverter os componentes do Lync Server 2013 para o Lync Server 2010 e, em seguida, atualizar diretamente para o Skype for Business Server 2015. Nesse caso, você não poderá aproveitar a atualização in-loco e usará a coexistência direta entre o Lync Server 2010 e o Skype for Business Server 2015. Não há suporte para o Tri, mas há suporte para coexistência.  <br/> |
|Lync Server 2010  <br/> |Ative um novo pool do Skype for Business Server 2015 e migre os usuários para esse novo pool. Você pode então encerrar o pool antigo do Lync Server 2010. A atualização do Lync Server 2010 para o Skype for Business Server 2015 é semelhante à atualização do Lync Server 2010 para o Lync Server 2013. Consulte [migração do Lync server 2010 para o Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Escolha uma das duas opções: <br/>  Configurar um novo ambiente do Skype for Business Server 2015. <br/>  Ou se o hardware e o software atenderem aos requisitos do Skype for Business Server 2015, atualize para o Lync Server 2013 e, em seguida, atualize para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco. Para obter mais informações, consulte [Server Requirements for Skype for Business server 2015](requirements-for-your-environment/server-requirements.md) e [Migration from Office communications Server 2007 R2 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> O SQL Server 2014 é suportado no Skype for Business Server 2015, mas não tem suporte no Lync Server 2013. Se você deseja atualizar do SQL Server 2012 para o SQL Server 2014, o pool deve primeiro ser atualizado para o Skype for Business Server 2015 usando o método de atualização in-loco, conforme descrito neste documento. Você pode então atualizar do SQL Server 2012 para o SQL Server 2014, consulte [upgrade to SQL server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx). Para saber mais sobre os requisitos de banco de dados, consulte [Server Requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planejar a atualização do Lync Server 2013 para o Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode atualizar os sistemas do Lync Server 2013 para o Skype for Business Server 2015 usando o novo recurso de atualização in-loco. A atualização in-loco oferece uma solução de clique única que faz o backup de certificados, desinstala componentes de servidor, atualiza os bancos de dados locais e instala as funções do Skype for Business Server 2015. A atualização in-loco busca preservar os investimentos existentes de hardware e de servidor, reduzindo o custo geral para implantar o Skype for Business Server 2015.
  
> [!NOTE]
> A atualização in-loco permite que você use o mesmo hardware ao atualizar para o Skype for Business Server. No entanto, reutilizar o mesmo hardware não é convertido na mesma capacidade de desempenho. Você não deve esperar que as cargas de desempenho do Lync Server 2013 e do Skype for Business Server 2015 sejam idênticas. 
  
> [!NOTE]
> A atualização in-loco não é compatível com alta disponibilidade ou recuperação de desastres para o Skype for Business Server. 
  
A atualização in-loco envolve pegar o pool do Lync Server 2013 offline e atualizá-lo para um pool 2015 do Skype for Business Server. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Criar um plano de atualização in-loco

Faça um plano que inclua:
  
1. Uma compreensão da sua topologia atual.
    
    > [!NOTE]
    > Não se esqueça de desinstalar a ferramenta de administração do LRS para o Lync Server 2013 antes de executar a atualização in-loco. A ferramenta de administração do LRS para Lync Server 2013 não pode coexistir com o Skype for Business Server 2015. Após a execução da atualização in-loco, instale a nova ferramenta de administração do LRS. Consulte [portal da Web administrativo do sistema de salas do Microsoft Lync para o Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) para obter mais detalhes.
  
2. O pool primário da atualização.
    
3. Se você vai atualizar os bancos de dados de arquivamento e monitoramento ou criar novos.
    
4. O método de atualização in-loco que você usará: offline ou move users. Como parte de mover os usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. 
    
5. Um plano de comunicação para os usuários afetados.
    
6. Um plano de backup caso as atualizações falhem.
    
Qualquer usuário que esteja no pool primário enquanto ele estiver sendo atualizado não poderá usar os serviços até que a atualização esteja concluída. Se você tiver um pool secundário de trabalho, poderá evitar o impacto dos usuários movendo-os para o pool secundário antes da atualização. Após a atualização, mova os usuários de volta para o pool principal.
  
### <a name="in-place-upgrade-methods"></a>Métodos de atualização in-loco

Há dois cenários para a atualização in-loco: 
  
- O método move User, que não requer tempo de inatividade para os usuários. 
    
- O método offline, que requer tempo de inatividade.
    
Recomendamos que uma atualização de método offline seja agendada durante uma janela de manutenção e que os usuários sejam notificados do tempo de inatividade.
  
> [!NOTE]
> Ao atualizar um pool emparelhado no Lync Server 2013 e você deseja atualizar os dois pools para o Skype for Business Server 2015. Certifique-se de atualizar o segundo pool imediatamente após atualizar o primeiro pool. Quando um pool está executando o Lync Server 2013 e o segundo pool está executando o Skype for Business Server 2015, as opções de recuperação de desastre são minimizadas. Por exemplo, se um pool estiver sendo executado 2013 e o segundo for 2015 e se houver um desastre, você poderá ter perda de dados, pois o failover do pool não é suportado no modo de desastre quando pools emparelhados não são da mesma versão. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método offline de atualização in-loco

Use este método se você não deseja mover os usuários entre os pools de usuários. Durante a atualização, os usuários não poderão usar o Lync ou o Skype for Business Services. 
  
O diagrama a seguir mostra uma visão geral desse processo.
  
![Lync 2013 para usuários do Skype offline](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Se você tiver pools emparelhados, não os desemparelhará antes da atualização. 
  
Depois de começar a atualizar um pool de servidores, você deve concluir a atualização de todo o pool. O Skype for Business Server não dá suporte para a atualização de apenas uma parte do pool. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Move Users (sem tempo de inatividade do usuário)
<a name="bkmk_MoveUsersMethod"> </a>

Para usar esse método, você move os usuários para outro pool antes de iniciar a atualização. Durante a atualização, os usuários podem usar os serviços do Lync. Após serem movidos para o pool atualizado, eles podem usar o Skype for Business. O diagrama a seguir mostra uma visão geral desse processo.
  
> [!IMPORTANT]
> Como parte de mover os usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. A conferência de discagem PSTN ainda resolverá o Conferenceid para o pool que está sendo atualizado, em vez do pool emparelhado. Portanto, você precisa mover os diretórios de conferência, se ainda quiser que conferências PSTNs agendadas no pool possam ser acessadas durante a atualização. 
  
![Diagrama de baixo que mostra os usuários que estão sendo movidos para outro pool antes que o pool seja atualizado e movido de volta para o pool após a atualização.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover usuários para atualização de hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Se o seu hardware não atender aos [requisitos do servidor do Skype for Business server 2015](requirements-for-your-environment/server-requirements.md), configure um novo ambiente do Skype for business Server 2015 e mova os usuários para lá. O diagrama a seguir mostra uma visão geral desse processo para atualização do Lync Server 2010. 
  
![Diagrama de pista de tela que mostra os usuários no pool de front-ends primário do Lync Server sendo movidos para o Skype for Business Server 2015 e o pool do Lync Server sendo descomissionado.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processo de atualização in-loco

 Atualize do Lync Server 2013 para o Skype for Business Server 2015 usando as seguintes etapas:
  
1. Faça backup de todos os bancos de dados antes da atualização.
    
2. Certifique-se de que todos os serviços que devem ser atualizados estejam em estado de execução.
    
3. Atualize e publique o arquivo de topologia usando o construtor de topologias.
    
4. Pare todos os serviços em todos os servidores front-end.
    
5. Instale novos pré-requisitos necessários para o Skype for Business Server.
    
6. Em cada servidor de front-end, inicie a atualização in-loco.
    
7. Quando a atualização estiver concluída, reinicie todos os serviços.
    
   - Para o pool de front-ends, reinicie os serviços usando o comando Start-CsPool.
    
   - Para servidores não front-end, use Start-CSWindowsService.
    
> [!NOTE]
>  Se você não quiser atualizar seus bancos de dados de arquivamento e monitoramento existentes, remova a dependência antes de atualizar a topologia. Se você deseja criar novos bancos de dados de arquivamento e monitoramento, durante a atualização, você pode criar um novo repositório SQL e associá-lo ao pool. Você pode encontrar as etapas sobre como fazer isso no tópico[atualizar para o Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > atualização in-loco não é compatível com alta disponibilidade ou recuperação de desastre para o Skype for Business Server. Para evitar a interrupção dos serviços dos usuários, use o [método move Users (sem tempo de inatividade do usuário)](upgrade.md#bkmk_MoveUsersMethod) para atualizar. > durante o processo de atualização, a réplica XDS é colocada na pasta compartilhada local na unidade de disco com mais espaço livre. Se esse disco for removido posteriormente, você poderá encontrar problemas como os serviços que não são iniciados.
  
### <a name="upgrade-order"></a>Ordem de atualização

Atualize a topologia de dentro para fora. Atualize primeiro todos os pools, depois os servidores de borda e, por fim, o pool do repositório de gerenciamento central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Considerações sobre a autenticação Kerberos

Se você usar a autenticação Kerberos para serviços Web, deverá reatribuir as contas Kerberos e redefinir a senha após a conclusão da atualização in-loco. Para saber como fazer isso, confira [Configurando a autenticação Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Suporte à coexistência com o Lync Server 2013 e o Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode executar o Skype for Business Server 2015 na mesma topologia que o Lync Server 2013 ou o Lync Server 2010, mas não pode ter todos os três na mesma topologia.
  
Se você tiver uma coexistência entre o Lync Server 2010 e o Lync Server 2013, é recomendável atualizar toda a topologia para o Lync Server 2013 e, em seguida, atualizar para o Skype for Business Server 2015 usando a atualização in-loco. Para obter mais informações, consulte [migração do Lync server 2010 para o Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Se sua topologia for principalmente o Lync Server 2010, reverta os componentes do Lync Server 2013 para o Lync Server 2010 antes de atualizar a topologia para o Skype for Business Server 2015. Nesse caso, você perde o benefício da atualização in-loco e tem uma topologia de coexistência entre o Lync Server 2010 e o Skype for Business Server 2015.
  
O diagrama a seguir mostra o suporte de coexistência do Skype for Business Server 2015 com o Lync Server 2013 e o Lync Server 2010.
  
![Um diagrama mostrando o suporte de coexistência do Skype for Business Server 2015 com o Lync Server 2013 ou o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processo de atualização com o servidor e o aplicativo de filial persistente existentes
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

O Skype for Business Server 2015 não oferece suporte a uma atualização in-loco de um aparelho de filial persistente (SBA) ou de um servidor de filial persistente (SBS).
  
No entanto, damos suporte à coexistência de datacenters do Skype for Business Server com o Lync Server 2010 ou o Lync Server 2013 SBA/SBS. 
  
Ao planejar uma atualização in-loco de um pool de front-ends (FE) do Lync Server 2013 com uma ramificação associada, você pode deixar os usuários existentes no Lync Server 2013 SBA/SBS. Durante a atualização, os usuários do SBA/SBS entrarão no modo de resiliência e retornarão à funcionalidade normal após a conclusão da atualização. Para obter mais informações sobre a experiência dos usuários durante o modo de resiliência, consulte [recursos de resiliência de site de filial no Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Ao migrar uma topologia do Lync Server 2010 para o Skype for Business Server 2015, o SBA/SBS deve ser adicionado novamente à topologia, semelhante à migração para o Lync Server 2013. Para as etapas necessárias, leia [conectar aparelho de filial persistente ao pool de front-ends do Lync Server 2013](https://technet.microsoft.com/library/jj688026.aspx).
  
Para topologias de coexistência do Lync Server 2010 e do Lync Server 2013, alinhe primeiro às recomendações feitas na seção ' suporte à coexistência com o Lync Server 2013 e o Lync Server 2010 '.
  
## <a name="see-also"></a>Confira também
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Atualização para o Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Requisitos ambientais para o Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Requisitos de servidor para o Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
