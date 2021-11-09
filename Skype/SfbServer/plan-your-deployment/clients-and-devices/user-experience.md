---
title: Planejar a Skype for Business do cliente 2015 para seus usuários
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Resumo: saiba mais sobre o novo Skype for Business e as etapas que você pode tomar para preparar seu ambiente e seus usuários para a atualização, se você está usando o Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 ou Lync Server 2010.'
ms.openlocfilehash: 9979b7d9fe449de926358097b9fd2fdd36e5afb4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864738"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planejar a Skype for Business do cliente 2015 para seus usuários
 
**Resumo:** Saiba mais sobre o novo Skype for Business e as etapas que você pode seguir para preparar seu ambiente e seus usuários para a atualização, se você está usando o Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013 ou Lync Server 2010.
  
A atualização de 14 de abril de 2015 Office Lync 2013 inclui a nova interface de usuário Skype for Business de usuário. Essa atualização permite que os administradores controlem a aparência do cliente e escolham se mantêm a experiência do cliente do Lync 2013 ou usam a experiência de cliente Skype for Business aprimorada. O cliente Skype for Business substituiu efetivamente o cliente Lync 2013 e adicionou a capacidade de os administradores escolherem entre a experiência de cliente existente do Lync e a nova experiência do cliente Skype for Business cliente. Para obter informações sobre essa atualização, consulte [April 14, 2015 update for Lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/kb/2889923/).
  
Em 12 de maio de 2015, haverá outra atualização mensal do Office que inclui o cliente Skype for Business atual. Muitos clientes que não aplicaram a atualização de abril receberão a atualização de 12 de maio para Office 2013. As informações neste tópico ajudarão você a preparar sua organização, seu ambiente e seus usuários para a atualização do cliente. Para facilitar a transição para seus usuários e equipes de suporte, use as informações neste tópico para ajudá-lo a decidir qual experiência de cliente deseja para seus usuários e, em seguida, fazer as alterações em seu ambiente antes de implantar a atualização do cliente em sua organização.
  
- [Qual experiência de cliente você deseja para seus usuários?](user-experience.md#clientexperience)
    
- [Preparar seu ambiente para o Skype for Business cliente](user-experience.md#usinglync)
    
- [Recursos para ajudá-lo a preparar suas equipes de suporte e seus usuários finais para a atualização](user-experience.md#support)
    
> [!NOTE]
> A experiência do cliente do Lync 2013 não é uma opção para Skype for Business versões do cliente 2016. Antes de tentar configurar seu ambiente cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não comece com o número 16; por exemplo: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Qual experiência de cliente você deseja para seus usuários?
<a name="clientexperience"> </a>

Com o novo Skype for Business cliente, você pode controlar qual experiência de cliente seus usuários obterão, Lync ou Skype for Business. A experiência padrão do cliente depende se você está usando o Lync ou Skype for Business local ou online. Se você estiver usando o Skype for Business Online (Lync Online) hoje com o Microsoft 365 Apps para Grandes Empresas, Microsoft 365 Business Standard ou Office 2013, a experiência do cliente Skype for Business atualizada, inspirada na aparência do Skype, será a experiência padrão do usuário. Se você estiver usando o Lync Server no local hoje, a experiência do cliente do Lync será o padrão.
  
Você pode configurar qual experiência de cliente seus usuários obter usando políticas de cliente. Uma política de cliente é um conjunto de configurações que são aplicadas aos usuários quando eles fazem logon no Lync ou Skype for Business.
  
### <a name="skype-for-business-client-experience"></a>Skype for Business cliente

Além de todos os recursos do Lync, o Skype for Business fornece novos recursos com controles simplificados e ícones familiares de Skype. Alguns novos recursos no Skype for Business estão disponíveis apenas com a nova experiência do Skype for Business cliente. Para saber mais sobre os novos recursos no Skype for Business, consulte [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiência do cliente do Lync

A experiência do cliente do Lync é muito semelhante à experiência do cliente do Lync 2013 com a qual os usuários já estão familiarizados, mas há algumas alterações que você deseja que seus usuários saibam. Para ver o que há de diferente entre a experiência do cliente do Lync e o cliente do Lync 2013, consulte Por que eu vejo Skype for Business quando estou usando o [Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) e os links adicionais mais adiante neste tópico.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar seu ambiente para o Skype for Business cliente
<a name="usinglync"> </a>

Há algumas coisas que você precisará fazer para preparar seu ambiente para a atualização do cliente. Antes de começar a fazer alterações para configurar a experiência do cliente, primeiro você precisa se certificar de que está usando uma versão do Skype for Business Server ou do Lync Server que oferece suporte às configurações de política do cliente.
  
Depois de confirmar que está usando uma versão do Skype for Business Server ou do Lync Server que oferece suporte às configurações de política para controlar a experiência do cliente, você precisará configurar as configurações de política em seu ambiente. As etapas específicas que você precisa seguir dependem da versão do Skype for Business Server ou do Lync Server que você está usando e se seus usuários estão no local ou online. 
  
Você vai querer fazer essas alterações antes que a atualização do cliente seja entregue aos usuários para que você possa controlar a experiência do cliente desde a primeira vez que eles iniciarem o cliente Skype for Business cliente. As tabelas a seguir apontam para as etapas que você precisa seguir para configurar seu ambiente para a experiência do cliente desejada para seus usuários.
  
|**Implantação**|**Skype for Business cliente**|**Experiência do cliente do Lync**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Não há etapas adicionais que não sejam implantar a com build do cliente 4711.1002 (abril de 2015) ou posterior.  <br/> |[Usar a experiência do cliente do Lync com o Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Não há etapas adicionais que não sejam implantar a com build do cliente 4711.1002 (abril de 2015) ou posterior.  <br/> |[Usar a experiência do cliente do Lync com Skype for Business Server local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 e Lync Server 2010  <br/> |[Usar a experiência Skype cliente com o Lync Server 2013 ou o Lync Server 2010 local](user-experience.md#SkypewithLynconprem) <br/> |[Usar a experiência do cliente do Lync com o Lync Server 2013 ou o Lync Server 2010 local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar a experiência Skype cliente com o Lync Server 2013 ou o Lync Server 2010 local
<a name="SkypewithLynconprem"> </a>

Siga as etapas nesta seção se você quiser configurar a experiência Skype cliente em uma implantação local. A experiência padrão para o local
  
 **Etapa 1:** Primeiro, certifique-se de que você está executando uma versão do Lync Server que dá suporte às configurações de política do cliente.
  
- **Lync Server 2013** - Você deve estar executando a Atualização Cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013 ou uma atualização posterior. Para obter informações, [consulte Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** - Você deve estar executando a Atualização Cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010 ou uma atualização posterior. Para obter informações, [consulte Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Etapa 2:** Em seguida, use uma política de cliente para definir a experiência Skype cliente com o cliente Skype for Business cliente. Há **três opções para usar** uma política de cliente para definir a experiência do cliente.
  
  **Opção 1:** De definir a Skype cliente usando uma política Global. Observe que a política Global se aplica a todos os usuários em sua implantação, mas as políticas de nível de usuário e de site têm precedência sobre a política Global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opção 2:** Modifique uma política de cliente existente que você está usando em seu ambiente para incluir a configuração para habilitar a experiência Skype cliente. Isso permite atribuir a experiência Skype cliente somente aos usuários que têm a política existente atribuída:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opção 3:** Crie uma nova política para atribuir aos usuários que incluam a configuração para a experiência Skype cliente. Primeiro, crie a nova política de cliente e forneça o nome da política como o valor do parâmetro **Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Em seguida, atribua a política aos usuários, usando o nome da política (o valor usado para o parâmetro **Identity)** como o valor do **parâmetro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Etapa 3:** Depois de configurar suas políticas de cliente, implante o cliente Skype for Business, build 4711.1002 (abril de 2015) ou posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar a experiência do cliente do Lync com o Lync Server 2013 ou o Lync Server 2010 local
<a name="LyncwithLynconprem"> </a>

Essa é a experiência padrão quando o cliente Skype for Business é implantado em uma implantação local do Lync Server. Você não precisa configurar nenhuma política de cliente para usar a experiência do cliente do Lync, mas talvez você queira controlar o primeiro comportamento de executar para o cliente. Por padrão, na primeira vez que os usuários iniciam o cliente Skype for Business, a experiência do cliente Skype é usada e uma notificação é exibida para os usuários que solicitam que eles reiniciem o cliente para obter a experiência do cliente do Lync. Você pode configurar seu ambiente para que a experiência do cliente do Lync seja exibida na primeira vez que os usuários iniciarem o cliente, bem como desativar o tutorial do cliente modificando o registro do sistema em computadores cliente. Para as etapas que você precisa executar antes de implantar o cliente Skype for Business, consulte um dos seguintes tópicos:
  
- **Lync Server 2013**, consulte [Configure the client experience with Skype for Business in Lync Server 2013](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **Lync Server 2010** consulte [Configure the client experience with Skype for Business in Lync Server 2010](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar a experiência do cliente do Lync com Skype for Business Server local
<a name="LyncwithSfBServer"> </a>

Siga as etapas nesta seção se você quiser configurar a experiência do cliente do Lync em uma implantação Skype for Business Server local.
  
Siga as etapas nesta seção se você quiser configurar a experiência Skype cliente em uma implantação local. A experiência padrão para o local
  
 **Etapa 1:** Primeiro, implante Skype for Business Server.
  
 **Etapa 2:** Em seguida, use uma política de cliente para definir a experiência do cliente do Lync com o cliente Skype for Business cliente. Há **três opções para usar** uma política de cliente para definir a experiência do cliente.
  
 **Opção 1:** De definir a experiência do cliente do Lync usando uma política Global. Observe que a política Global se aplica a todos os usuários em sua implantação, mas as políticas de nível de usuário e de site têm precedência sobre a política Global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opção 2:** Modifique uma política de cliente existente que você está usando em seu ambiente para incluir a configuração para habilitar a experiência do cliente do Lync. Isso permite atribuir a experiência do cliente do Lync somente aos usuários que têm a política existente atribuída:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opção 3:** Crie uma nova política para atribuir aos usuários que incluam a configuração da experiência do cliente do Lync. Primeiro, crie a nova política de cliente e forneça o nome da política como o valor do parâmetro **Identity:**
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Em seguida, atribua a política aos usuários, usando o nome da política (o valor usado para o parâmetro **Identity)** como o valor do **parâmetro PolicyName:**
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Etapa 3:** Opcional - Por padrão, na primeira vez que os usuários iniciam o cliente Skype for Business, a experiência do cliente Skype é usada e uma notificação é exibida para os usuários solicitando que eles reiniciem o cliente para obter a experiência do cliente do Lync. Você pode configurar seu ambiente para que a experiência do cliente do Lync seja exibida na primeira vez que os usuários iniciarem o cliente, bem como desativar o tutorial do cliente modificando o registro do sistema em computadores cliente. Para as etapas que você precisa executar antes de implantar o cliente Skype for Business, consulte [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Etapa 4:** Depois de configurar suas políticas de cliente, implante o cliente Skype for Business, build 4711.1002 (abril de 2015) ou posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar a experiência do cliente do Lync com o Skype for Business Online
<a name="LyncwithSfBO"> </a>

Siga as etapas nesta seção se você quiser configurar a experiência do cliente do Lync e usar o Skype for Business Online.
  
Se você estiver usando o Skype for Business Online, ainda poderá usar a experiência do cliente do Lync com o cliente Skype for Business em sua organização usando o PowerShell Remoto para configurar políticas de cliente. Há **três opções para usar** uma política de cliente para definir a experiência do cliente. Observe que os nomes de política e parâmetro são diferentes das configurações que você usa para configurar a experiência do cliente quando você está usando o Skype for Business ou o Lync Server local.
  
 **Opção 1:** De definir a experiência do cliente do Lync usando uma política Global. Observe que as políticas de cliente e site aplicadas aos usuários terão precedência sobre uma política Global.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opção 2:** Modifique uma política de cliente existente que você está usando em seu ambiente para incluir a configuração para habilitar a experiência do cliente do Lync. Isso permite atribuir a experiência do cliente do Lync somente aos usuários que têm a política existente atribuída:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opção 3:** Use uma instância de política personalizada que inclua a configuração da experiência do cliente do Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Depois de configurar suas políticas de cliente, implante o cliente Skype for Business, build 4711.1002 (abril de 2015) ou posterior.
  
Para obter informações detalhadas sobre como configurar a experiência do cliente com o Skype for Business Online, incluindo etapas sobre como controlar a primeira experiência de executar e os scripts do PowerShell que você pode usar para configurar seu ambiente, consulte Alternando entre o Skype for Business e as interfaces do usuário cliente [do Lync.](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md)
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos para ajudá-lo a preparar suas equipes de suporte e seus usuários finais para a atualização
<a name="support"> </a>

Para facilitar a preparação para a transição, temos muitos recursos adicionais disponíveis para ajudá-lo a planejar, instruir e envolver usuários finais.
  
- [Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype for Business Guias de Início Rápido (Download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [O Lync agora Skype for Business — veja as novidades](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: guia passo a passo para novos usuários](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Por que vejo Skype for Business quando estou usando o Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
