---
title: Excluir um conjunto existente das configurações do Tronco SIP no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Resumo: Saiba como excluir uma coleção de definições de configuração do tronco usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: 64831efe35880b3e211543c80d9ba00939128354
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a>Excluir um conjunto existente das configurações do Tronco SIP no Skype for Business Server 2015
 
**Resumo:** Saiba como excluir um conjunto de definições de configuração do tronco usando o Skype para painel de controle do servidor de negócios.
  
As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:
  
- Se o desvio de mídia deve ser ativado nos troncos.
    
- As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.
    
- Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.
    
Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Este conjunto global de configurações não pode ser excluído. No entanto, você pode usar o Skype para painel de controle do Business Server ou o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) "Redefinir" as propriedades na coleção global para seus valores padrão. Por exemplo, se a propriedade Enable3pccRefer foi definida como Verdadeira, quando o conjunto global for redefinido, a propriedade Enable3pccRefer será revertida para o valor padrão Falso.
  
Os administradores também podem criar definições personalizadas de configuração de tronco no escopo do site ou escopo do serviço (para um gateway PSDN individual); essas configurações padrão podem ser removidas. Ao remover essas configurações padrão, lembre-se do seguinte:
  
- Se você remover as configurações do escopo do serviço, o tronco SIP gerenciado por essas configurações será gerenciado pelas configurações aplicadas ao site, caso existam. Se as configurações não existirem, esses troncos serão então gerenciados pelo conjunto global de definições de configuração do tronco.
    
- Se você remover as configurações pertencentes ao escopo do site, todos os troncos SIP gerenciados por essas configurações serão então gerenciados pelo conjunto global de definições de configuração do tronco.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Para remover as definições de configuração do tronco com Skype para painel de controle do servidor de negócios

1. No painel de controle do servidor de negócios do Skype, clique em **Roteamento de voz** e clique em **Configuração do tronco**.
    
2. Na guia **Configuração do Tronco**, selecione o conjunto de definições de configuração do tronco SIP a ser excluído, clique em **Editar** e, então, clique em **Excluir**. Para excluir vários conjuntos na mesma operação, clique no primeiro conjunto a ser excluído, mantenha pressionada a tecla Ctrl e clique em todos os outros conjuntos que deseja remover.
    
3. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
    
4. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
    
5. Na caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.
    
6. Se mudar de ideia e decidir não excluir o conjunto, clique em **Confirmar** e, depois, em **Cancelar todas as alterações não confirmadas**. Quando for exibida a caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Removendo definições de configuração de tronco usando Skype para Cmdlets do Shell de gerenciamento de servidor de negócios

Você pode excluir as definições de configuração de tronco usando Skype para o Shell de gerenciamento de servidor de negócios e o cmdlet **Remove-CsTrunkConfiguration** . Você pode executar esse cmdlet seja do Skype para Business Server Management Shell ou de uma sessão remota do Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Para remover uma coleção especificada das definições

- O seguinte comando remove as definições de configuração do tronco aplicadas ao site Redmond:
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Para remover todos os conjuntos aplicados ao escopo do site

- Este comando remove todas as definições de configuração do tronco aplicadas ao escopo do serviço:
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Para remover todos os conjuntos em que o bypass de mídia está habilitado

- O seguinte comando remove todas as definições de configuração do tronco em que o desvio de mídia está habilitado:
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .
  

