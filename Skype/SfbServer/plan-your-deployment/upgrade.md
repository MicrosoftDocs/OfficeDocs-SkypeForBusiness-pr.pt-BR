---
title: Planejar a atualização para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: Saiba mais sobre o que você deve considerar ao planejar uma atualização para o Skype for Business Server 2015. Baixe uma avaliação gratuita do Skype for Business Server 2015 do Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 69b1d9df20330ad0baecbc1c5abe59e76808185a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831971"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planejar a atualização para o Skype for Business Server 2015
 
Resumo: Saiba mais sobre o que você deve considerar ao planejar uma atualização para o Skype for Business Server 2015. Baixe uma avaliação gratuita do Skype for Business Server 2015 do Centro de Avaliação da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Como parte do seu plano de atualização para o Skype for Business Server 2015, use este tópico para entender os caminhos de atualização recomendados para o Skype for Business Server 2015, como funciona a atualização do In-Place, como são os cenários de coexistência com suporte e como é o processo de atualização.

> [!NOTE]
> As atualizações in-place estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. A coexistência lado a lado é suportada, confira Migração para [o Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Caminhos de atualização recomendados para o Skype for Business Server 2015

 Para atualizar do Lync Server 2013, Lync Server 2010 ou Office Communications Server 2007 R2 para o Skype for Business Server 2015, use os seguintes caminhos de atualização:
  
> [!CAUTION]
> In-Place Upgrade move automaticamente os diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015. No entanto, se você planeja mover manualmente os diretórios de conferência, é muito importante usar o Shell de Gerenciamento do Skype for Business Server 2015. Se você tentar usar o Shell de Gerenciamento do Lync Server 2013 para mover diretórios de conferência do Lync Server 2013 para o Skype for Business Server 2015, poderá ocorrer perda de dados. Em geral, sempre que você estiver trabalhando com o Skype for Business Server 2015 em qualquer capacidade, deverá usar o conjunto de ferramentas do Skype for Business Server 2015.  
  
|**Versão**|**Recomendações**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para atualizar, use o Construtor de Topologias do Skype for Business Server e o novo recurso In-Place atualização em cada um dos servidores associados ao pool. consulte [Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and Upgrade to Skype for Business Server [2015](../deploy/upgrade-to-skype-for-business-server.md) for detailed steps. <br/> |
|Lync Server 2010 + Lync Server 2013 (modo duplo)  <br/> |Primeiro, atualize para o Lync Server 2013 e depois atualize para o Skype for Business Server 2015 usando o novo recurso In-Place Atualização. No entanto, se sua topologia for o Lync Server 2010 principal, você também poderá reverter os componentes do Lync Server 2013 para o Lync Server 2010 e atualizar diretamente para o Skype for Business Server 2015. Nesse caso, você não seria capaz de tirar proveito da atualização do In-Place e usaria a co-existência direta entre o Lync Server 2010 e o Skype for Business Server 2015. A tri existência não é suportada, mas a co-existência é suportada.  <br/> |
|Lync Server 2010  <br/> |Traga um novo pool do Skype for Business Server 2015 e migre os usuários para esse novo pool. Em seguida, você pode descomissionar o pool antigo do Lync Server 2010. A atualização do Lync Server 2010 para o Skype for Business Server 2015 é semelhante à atualização do Lync Server 2010 para o Lync Server 2013. Consulte [Migração do Lync Server 2010 para o Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=526615)  <br/> |
|Office Communications Server 2007 R2  <br/> | Escolha uma das duas opções: <br/>  Configurar um novo ambiente do Skype for Business Server 2015. <br/>  Ou, se seu hardware e software atenderem aos requisitos do Skype for Business Server 2015, atualize para o Lync Server 2013 e atualize para o Skype for Business Server 2015 usando o novo recurso de atualização In-Place. Para obter mais informações, consulte Requisitos de servidor do [Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) e migração do Office Communications Server [2007 R2 para o Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=526616)  <br/> |
   
> [!NOTE]
> O SQL Server 2014 é suportado no Skype for Business Server 2015, mas não é suportado no Lync Server 2013. Se você deseja atualizar do SQL Server 2012 para o SQL Server 2014, o pool deve primeiro ser atualizado para o Skype for Business Server 2015 usando o método In-Place Upgrade conforme descrito neste documento. Em seguida, você pode atualizar do SQL Server 2012 para o SQL Server 2014, consulte Atualização para [o SQL Server 2014.](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx) Para saber mais sobre os requisitos de banco de dados, [consulte Requisitos de servidor para o Skype for Business Server 2015.](requirements-for-your-environment/server-requirements.md) 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planejar a atualização do Lync Server 2013 para o Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode atualizar os sistemas do Lync Server 2013 para o Skype for Business Server 2015 usando o novo recurso In-Place Atualização. A atualização local fornece uma solução de um clique que faz o back up de certificados, desinstala componentes de servidor, atualiza bancos de dados locais e instala as funções do Skype for Business Server 2015. A atualização local procura preservar os investimentos existentes em hardware e servidor, reduzindo o custo geral para implantar o Skype for Business Server 2015.
  
> [!NOTE]
> In-Place Upgrade permite que você use o mesmo hardware ao atualizar para o Skype for Business Server. No entanto, o reutilizamento do mesmo hardware não se traduz na mesma capacidade de desempenho. Você não deve esperar que as cargas de desempenho do Lync Server 2013 e do Skype for Business Server 2015 sejam idênticas. 
  
> [!NOTE]
> In-Place atualização não suporta alta disponibilidade ou recuperação de desastres para o Skype for Business Server. 
  
A atualização local envolve colocar o pool do Lync Server 2013 offline e atualizando-o para um pool do Skype for Business Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Criar um plano In-Place Atualização

Faça um plano que inclua:
  
1. Noções básicas sobre sua topologia atual.
    
    > [!NOTE]
    > Certifique-se de desinstalar a ferramenta de Administração do LRS para o Lync Server 2013 antes de executar In-Place Atualização. A Ferramenta de Administração do LRS para Lync Server 2013 não pode coexistir com o Skype for Business Server 2015. Após executar In-Place Atualização, instale a nova ferramenta LRS Admin. Consulte [Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) para obter mais detalhes.
  
2. O pool principal da atualização.
    
3. Se você atualizará os bancos de dados de Arquivamento e Monitoramento ou criará novos.
    
4. O In-Place upgrade de usuário que você usará: Offline ou Mover Usuários. Como parte de Mover Usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. 
    
5. Um plano de comunicação para usuários afetados.
    
6. Um plano de backup caso as atualizações falhem.
    
Todos os usuários que estão no pool principal enquanto ele está sendo atualizado não poderão usar os serviços até que a atualização seja concluída. Se você tiver um pool secundário em funcionamento, poderá evitar afetar os usuários movendo-os para o pool secundário antes da atualização. Após a atualização, mova os usuários de volta para o pool primário.
  
### <a name="in-place-upgrade-methods"></a>Métodos de atualização in-place

Há dois cenários para a In-Place Atualização: 
  
- O método Mover Usuário, que não requer tempo de inatividade para os usuários. 
    
- O método Offline, que requer tempo de inatividade.
    
Recomendamos que uma atualização do método Offline seja agendada durante uma janela de manutenção e que os usuários sejam notificados sobre o tempo de inatividade.
  
> [!NOTE]
> Ao atualizar um pool emparelhado no Lync Server 2013 e você deseja atualizar ambos os pools para o Skype for Business Server 2015. Certifique-se de atualizar o segundo pool imediatamente após atualizar o primeiro pool. Quando um pool está executando o Lync Server 2013 e o segundo pool está executando o Skype for Business Server 2015, as opções de recuperação de desastres são minimizadas. Por exemplo, se um pool estiver executando 2013 e o segundo for 2015 e houver um desastre, você poderá experimentar perda de dados porque o failover do pool não é suportado no modo de desastre quando pools emparelhados não são da mesma versão. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método Offline de atualização no local

Use esse método se não quiser mover usuários entre pools de usuários. Durante a atualização, os usuários não poderão usar os serviços do Lync ou do Skype for Business. 
  
O diagrama a seguir mostra uma visão geral desse processo.
  
![Lync 2013 para usuários do Skype offline](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Se você tiver pools emparelhados, não os desempacoe antes da atualização. 
  
Depois de iniciar a atualização de um pool de servidores, você deve concluir a atualização do pool inteiro. O Skype for Business Server não dá suporte à atualização de apenas uma parte do pool. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Move Users (sem tempo de inatividade do usuário)
<a name="bkmk_MoveUsersMethod"> </a>

Para usar esse método, mova os usuários para outro pool antes de iniciar a atualização. Durante a atualização, os usuários podem usar os serviços do Lync. Depois que eles são movidos para o pool atualizado, eles podem usar o Skype for Business. O diagrama a seguir mostra uma visão geral desse processo.
  
> [!IMPORTANT]
> Como parte de Mover Usuários, você também precisará migrar os diretórios de conferência global associados ao pool primário. A conferência discada PSTN ainda resolverá o ConferenceID para o pool que está sendo atualizado, em vez do pool emparelhado. Portanto, você precisará mover os Diretórios de Conferência, se ainda quiser que as conferências PSTN agendadas no pool sejam acessíveis durante a atualização. 
  
![Diagrama de diagrama que mostra os usuários sendo movidos para outro pool antes que o pool seja atualizado e movido de volta para o pool após a atualização.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover usuários para atualização de hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Se o hardware não atender aos requisitos de servidor do [Skype for Business Server 2015,](requirements-for-your-environment/server-requirements.md)de configurar um novo ambiente do Skype for Business Server 2015 e mover os usuários para lá. O diagrama a seguir mostra uma visão geral desse processo para atualização do Lync Server 2010. 
  
![Diagrama de diagrama que mostra os usuários no pool de front-end primário do Lync Server sendo movido para o Skype for Business Server 2015 e o pool do Lync Server sendo desativado.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processo de atualização in-loco

 Atualização do Lync Server 2013 para o Skype for Business Server 2015 usando as seguintes etapas:
  
1. Faça o back up de todos os bancos de dados antes da atualização.
    
2. Certifique-se de que todos os serviços que devem ser atualizados estão em estado de execução.
    
3. Atualize e publique o arquivo de topologia usando o construtor de topologias.
    
4. Pare todos os serviços em todos os servidores front-end.
    
5. Instale os novos pré-requisitos necessários para o Skype for Business Server.
    
6. Em cada servidor front-end, inicie o In-Place Atualização.
    
7. Quando a atualização for concluída, reinicie todos os serviços.
    
   - Para o pool de Front-End, reinicie os serviços usando o comando Start-CsPool.
    
   - Para servidores que não são front-end, use Start-CSWindowsService.
    
> [!NOTE]
>  Se você não quiser atualizar seus bancos de dados de Arquivamento e Monitoramento existentes, remova a dependência antes de atualizar a topologia. Se você quiser criar novos bancos de dados de Arquivamento e Monitoramento, durante a atualização, poderá criar um novo armazenamento SQL e associá-lo ao pool. Você pode encontrar as etapas sobre como fazer isso no tópico Upgrade[to Skype for Business Server 2015.](../deploy/upgrade-to-skype-for-business-server.md) > atualização local não suporta alta disponibilidade ou recuperação de desastre para o Skype for Business Server. Para evitar interromper os serviços dos usuários, use o método [Move Users (sem](upgrade.md#bkmk_MoveUsersMethod) tempo de inatividade do usuário) para atualizar.> Durante o processo de atualização, a réplica xds é colocada na pasta compartilhada local na unidade de disco com mais espaço livre. Se esse disco for removido posteriormente, você poderá ter problemas como serviços que não estão iniciando.
  
### <a name="upgrade-order"></a>Ordem de atualização

Atualize a topologia de dentro para fora. Atualize todos os seus pools primeiro, depois os servidores de borda e, finalmente, o pool do CmS (Armazenamento de Gerenciamento Central). 
  
### <a name="kerberos-authentication-considerations"></a>Considerações sobre a autenticação Kerberos

Se você usar a autenticação Kerberos para Serviços Web, deverá reatribuir contas Kerberos e redefinir a senha após a conclusão In-Place Atualização. Para saber como fazer isso, consulte [Configurando a autenticação Kerberos.](https://go.microsoft.com/fwlink/p/?LinkId=530342)
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Suporte para coexistência com o Lync Server 2013 e o Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Você pode executar o Skype for Business Server 2015 na mesma topologia que o Lync Server 2013 ou o Lync Server 2010, mas não pode ter todos os três na mesma topologia.
  
Se você tiver uma cooperação entre o Lync Server 2010 e o Lync Server 2013, é recomendável atualizar a topologia inteira para o Lync Server 2013 e atualizar para o Skype for Business Server 2015 usando a Atualização In-Place. Para obter mais informações, [consulte Migração do Lync Server 2010 para o Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=526615)
  
Se sua topologia for principalmente o Lync Server 2010, reverter os componentes do Lync Server 2013 para o Lync Server 2010 antes de atualizar a topologia para o Skype for Business Server 2015. Nesse caso, você perde o benefício da atualização do In-Place e tem uma topologia de co-existência entre o Lync Server 2010 e o Skype for Business Server 2015.
  
O diagrama a seguir mostra o suporte de coexistência do Skype for Business Server 2015 com o Lync Server 2013 e o Lync Server 2010.
  
![Um diagrama mostrando suporte à coexistência do Skype for Business Server 2015 com o Lync Server 2013 ou o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processo de atualização com Servidor e Aparelho de Filial Existente
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

O Skype for Business Server 2015 não dá suporte a uma Atualização In-Place de um Aparelho de FilialVivível (SBA) ou um Servidor de Filial Survivável (SBS).
  
No entanto, suportamos a coexistência de datacenters do Skype for Business Server com o Lync Server 2010 ou o Lync Server 2013 SBA/SBS. 
  
Ao planejar uma atualização de In-Place de um pool de front-end (FE) do Lync Server 2013 com uma ramificação associada, você pode deixar os usuários existentes no Lync Server 2013 SBA/SBS. Durante a atualização, os usuários do SBA/SBS entrarão no modo de resiliência e retornarão à funcionalidade normal após a conclusão da atualização. Para obter mais informações sobre a experiência dos usuários durante o modo de resiliência, consulte recursos de resiliência do site de filial no [Lync Server 2013.](https://technet.microsoft.com/library/gg398715.aspx)
  
Ao migrar uma topologia do Lync Server 2010 para o Skype for Business Server 2015, o SBA/SBS deve ser adicionado à topologia, semelhante à migração para o Lync Server 2013. Para as etapas necessárias, leia [Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool](https://technet.microsoft.com/library/jj688026.aspx).
  
Para topologias de coexistência do Lync Server 2010 e do Lync Server 2013, alinhe primeiro as recomendações feitas na seção "Suporte para coexistência com o Lync Server 2013 e o Lync Server 2010".
  
## <a name="see-also"></a>Confira também
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Atualizar para o Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Requisitos ambientais do Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Requisitos de servidor para o Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
