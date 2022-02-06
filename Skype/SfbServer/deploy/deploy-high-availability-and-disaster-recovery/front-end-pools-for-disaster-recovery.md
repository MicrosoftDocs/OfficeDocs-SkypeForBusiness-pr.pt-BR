---
title: Implantar pools front-end emparelhados para recuperação de desastres Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 'Você pode optar por usar pools front-end emparelhados para fornecer proteção de recuperação de desastres, mas fazer isso não é um requisito.'
---

# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Implantar pools front-end emparelhados para recuperação de desastres Skype for Business Server
 
Você pode optar por usar pools front-end emparelhados para fornecer proteção de recuperação de desastres, mas fazer isso não é um requisito.
  
Você pode implantar facilmente a topologia de recuperação de desastres de pools front-end emparelhados usando o Construtor de Topologias. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Para implantar um par de pools do Front-End

1. Se os pools são novos e ainda não definidos, use o Construtor de Topologias para criar os pools.
    
2. No Construtor de Topologias, clique com o botão direito do mouse em um dos dois pools e clique em **Editar Propriedades**.
    
3. Clique em **Resiliência** no painel esquerdo e selecione **Pool de backup associado** no painel direito.
    
4. Na caixa abaixo **Pool de backup associado**, selecione o pool que você deseja emparelhar com este pool. Apenas pools existentes que não estão emparelhados com outro pool estarão disponíveis para selecionar.
    
5. Selecione **Failover automático e failback para voz** e clique em **OK**.
    
    Ao exibir os detalhes sobre este pool, o pool associado agora aparece no painel direito em **Resiliência**. 
    
6. Use o Construtor de Topologias para publicar a topologia.
    
7. Se os dois pools ainda não foram implantados, implante-os e a configuração estará concluída. Você pode ignorar as etapas finais deste procedimento.
    
    No entanto, se os pools já foram implantados antes de você definir o relacionamento emparelhado, você deve concluir as etapas finais a seguir.
    
8. Em cada Servidor de Front-End Server nos pools, execute o seguinte:
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    Isto configura outros serviços necessários para que o emparelhamento de backup funcione corretamente.
    
9. Depois que o Bootstrapper concluir a instalação dos componentes necessários para o emparelhamento de backup em todos os Servidores Front-end em ambos os pools, certifique-se de aplicar novamente qualquer Atualização Cumulativa existente que tenha sido aplicada anteriormente nesses Servidores Front-End em ambos os pools e continue com a próxima etapa.

10. Em um prompt Skype for Business Server de comando do Shell de Gerenciamento, execute o seguinte: 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Force o usuário e os dados de conferência de ambos os pools a serem sincronizados uns com os seguintes cmdlets:
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    Sincronizar os dados pode levar algum tempo. É possível usar os seguintes cmdlets para verificar os tatus. Certifique-se de que o status em ambas as direções está em estado estável.
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> A **opção failover e failback** automáticos para Voz e os intervalos de tempo associados no Construtor de Topologias aplicam-se apenas aos recursos de resiliência de voz introduzidos no Lync Server. Selecionar esta opção não implica que o failover de pool discutido neste documento seja automático. O failover de pool e failback sempre exige que um administrador invoque manualmente os cmdlets de failover e failback, respectivamente.
  
## <a name="see-also"></a>Confira também

[Recuperação de desastre de pool de front-end no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
