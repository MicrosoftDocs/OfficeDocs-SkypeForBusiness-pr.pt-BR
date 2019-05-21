---
title: Implantar pools de front-end emparelhados para recuperação de desastres no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Você pode usar pools de front-ends para fornecer proteção à recuperação de desastre, mas isso não é obrigatório.
ms.openlocfilehash: 49af49a4a8ff3dd0f543de6f1b13bfbe5b571788
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298505"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Implantar pools de front-end emparelhados para recuperação de desastres no Skype for Business Server
 
Você pode usar pools de front-ends para fornecer proteção à recuperação de desastre, mas isso não é obrigatório.
  
Você pode implantar facilmente a topologia de recuperação de desastres de pools front-end em par usando o construtor de topologias. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Para implantar um par de pools de front-ends

1. Se os pools forem novos e ainda não estiverem definidos, use o construtor de topologias para criar os grupos.
    
2. No construtor de topologias, clique com o botão direito do mouse em um dos dois grupos e clique em **Editar propriedades**.
    
3. Clique em **Resiliência** no painel esquerdo e selecione **Pool de Backup Associado** no painel direito.
    
4. Na caixa abaixo de **Pool de Backup Associado**, selecione o pool que você deseja emparelhar com este pool. Apenas pools existentes que não estejam emparelhados com outro pool estarão disponíveis para seleção.
    
5. Selecione **Failback e failover automático para Voz** e clique em **OK**.
    
    Quando você exibir os detalhes sobre este pool, o pool associado agora aparecerá no painel direito em **Resiliência**.  
    
6. Use o construtor de topologias para publicar a topologia.
    
7. Se os dois pools ainda não foram implantados, implante-os e a configuração estará concluída. Você pode ignorar as duas etapas finais deste procedimento.
    
    No entanto, se os pools já foram implantados antes de você definir a relação emparelhada, você deverá concluir as duas etapas finais a seguir.
    
8. Em cada Servidor Front-End nos pools, execute o seguinte:
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    Isso configura outros serviços necessários para que o emparelhamento de backup funcione corretamente.
    
9. Em um prompt de comando do Shell de gerenciamento do Skype for Business Server, execute o seguinte: 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. Force a sincronização dos dados do usuário e de conferência de ambos os pools com os seguintes cmdlets:
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    A sincronização dos dados pode levar algum tempo. É possível usar os cmdlets a seguir para verificar o status. O status em ambas as direções deve estar em um estado estável.
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> A opção **failover automático e failback para voz** e os intervalos de tempo associados no construtor de topologia só se aplicam aos recursos de resiliência de voz que foram introduzidos no Lync Server. Selecionar essa opção não implica que o failover de pool discutido neste documento seja automático. O failback e o failover de pool sempre exigem que um administrador invoque manualmente os cmdlets de failback e failover, respectivamente.
  
## <a name="see-also"></a>Confira também

[Recuperação de desastre do pool de front-end no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
