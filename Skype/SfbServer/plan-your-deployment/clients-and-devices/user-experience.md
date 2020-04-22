---
title: Planejar a experiência de cliente 2015 do Skype for Business para seus usuários
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
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
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Resumo: Saiba mais sobre o novo Skype for Business e as etapas que você pode executar para preparar seu ambiente e seus usuários para a atualização, se você está usando o Skype for Business Online, o Skype for Business Server 2019, o Skype for Business Server 2015, o Lync Server 2013 ou o Lync Server 2010.'
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777746"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planejar a experiência de cliente 2015 do Skype for Business para seus usuários
 
**Resumo:** Saiba mais sobre o novo Skype for Business e as etapas que você pode executar para preparar seu ambiente e seus usuários para a atualização, se você está usando o Skype for Business Online, o Skype for Business Server 2019, o Skype for Business Server 2015, o Lync Server 2013 ou o Lync Server 2010.
  
A atualização do Office de 14 de abril de 2015 do Lync 2013 inclui a nova interface de usuário do Skype for Business. Essa atualização permite que os administradores controlem a aparência do cliente e decidam se deseja manter a experiência do cliente do Lync 2013 ou usar a experiência aprimorada do cliente do Skype for Business. O cliente Skype for Business substituiu efetivamente o cliente Lync 2013 e adicionou a capacidade de os administradores escolherem entre a experiência de cliente do Lync existente e a nova experiência de cliente do Skype for Business. Para obter informações sobre essa atualização, consulte [atualização de 14 de abril de 2015 do Lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/kb/2889923/).
  
Em 12 de maio de 2015, haverá outra atualização mensal do Office que inclui o cliente do Skype for Business atualizado. Muitos clientes que não aplicaram a atualização de Abril vão pegar a atualização de 12 de maio para o Office 2013. As informações neste tópico ajudarão você a preparar sua organização, seu ambiente e seus usuários para a atualização do cliente. Para facilitar a transição para os usuários e suas equipes de suporte, use as informações neste tópico para ajudá-lo a decidir qual experiência de cliente você deseja para os usuários e faça as alterações em seu ambiente antes de implantar a atualização do cliente em sua organização.
  
- [Qual experiência do cliente você deseja para seus usuários?](user-experience.md#clientexperience)
    
- [Preparar seu ambiente para o cliente do Skype for Business](user-experience.md#usinglync)
    
- [Recursos para ajudá-lo a preparar suas equipes de suporte e seus usuários finais para a atualização](user-experience.md#support)
    
> [!NOTE]
> A experiência de cliente do Lync 2013 não é uma opção para as versões do cliente do Skype for Business 2016. Antes de tentar configurar seu ambiente de cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não inicie com o número 16; por exemplo: 16. x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Qual experiência do cliente você deseja para seus usuários?
<a name="clientexperience"> </a>

Com o novo cliente Skype for Business, você pode controlar qual experiência de cliente seus usuários receberão, Lync ou Skype for Business. A experiência do cliente padrão depende se você está usando o Lync ou o Skype for Business no local ou online. Se você estiver usando o Skype for Business online (Lync Online) hoje com o Microsoft 365 aplicativos para empresas, o Microsoft 365 Business Standard ou o Office 2013, a experiência atualizada de cliente do Skype for Business, inspirada pela aparência do Skype, será a experiência de usuário padrão. Se você estiver usando o Lync Server no local hoje, a experiência do cliente do Lync será o padrão.
  
Você pode configurar a experiência do cliente que os usuários recebem usando políticas de cliente. Uma política de cliente é um conjunto de definições de configuração que são aplicadas aos usuários quando eles fazem logon no Lync ou no Skype for Business.
  
### <a name="skype-for-business-client-experience"></a>Experiência de cliente do Skype for Business

Além de todos os recursos do Lync, o Skype for Business oferece novos recursos com controles simplificados e ícones familiares do Skype. Alguns recursos novos no Skype for Business estão disponíveis apenas com a nova experiência de cliente do Skype for Business. Para saber mais sobre os novos recursos do Skype for Business, consulte [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiência de cliente do Lync

A experiência de cliente do Lync é muito semelhante à experiência de cliente do Lync 2013 que seus usuários já estão familiarizados, mas há algumas alterações que você deseja permitir que seus usuários saibam. Para ver o que há de diferente entre a experiência de cliente do Lync e o cliente Lync 2013, confira [por que vejo o Skype for Business quando estou usando o Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) e os links adicionais mais adiante neste tópico.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar seu ambiente para o cliente do Skype for Business
<a name="usinglync"> </a>

Há algumas coisas que você precisará fazer para preparar o ambiente para a atualização do cliente. Antes de começar a fazer qualquer alteração para configurar a experiência do cliente, primeiro você precisa se certificar de que está usando uma versão do Skype for Business Server ou do Lync Server que oferece suporte às configurações de política do cliente.
  
Depois de confirmar que você está usando uma versão do Skype for Business Server ou Lync Server que oferece suporte às configurações de política para controlar a experiência do cliente, você precisará definir as configurações de política em seu ambiente. As etapas específicas que você precisa seguir dependem da versão do Skype for Business Server ou do Lync Server que você está usando e se os usuários estão no local ou online. 
  
Convém fazer essas alterações antes que a atualização do cliente seja entregue aos seus usuários para que você possa controlar a experiência do cliente na primeira vez em que iniciarem o cliente Skype for Business. As tabelas a seguir apontam para as etapas que você precisa seguir para configurar seu ambiente para a experiência de cliente desejada para seus usuários.
  
|**Implantação**|**Experiência de cliente do Skype for Business**|**Experiência de cliente do Lync**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Não há outras etapas além de implantar a compilação de cliente 4711,1002 (abril de 2015) ou posterior.  <br/> |[Usar a experiência de cliente do Lync com o Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Não há outras etapas além de implantar a compilação de cliente 4711,1002 (abril de 2015) ou posterior.  <br/> |[Usar a experiência de cliente do Lync com o Skype for Business Server no local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 e Lync Server 2010  <br/> |[Usar a experiência de cliente do Skype com o Lync Server 2013 ou o Lync Server 2010 local](user-experience.md#SkypewithLynconprem) <br/> |[Usar a experiência de cliente do Lync com o Lync Server 2013 ou o Lync Server 2010 local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar a experiência de cliente do Skype com o Lync Server 2013 ou o Lync Server 2010 local
<a name="SkypewithLynconprem"> </a>

Siga as etapas nesta seção se você quiser configurar a experiência de cliente do Skype em uma implantação local. A experiência padrão para o local
  
 **Etapa 1:** Primeiro, verifique se você está executando uma versão do Lync Server que oferece suporte às configurações de política do cliente.
  
- **Lync server 2013** -você deve estar executando a atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013 ou uma atualização posterior. Para obter informações, consulte [atualizações para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync server 2010** -você deve estar executando a atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010 ou uma atualização posterior. Para obter informações, consulte [atualizações para o Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
  **Etapa 2:** Em seguida, use uma política de cliente para definir a experiência de cliente do Skype com o cliente Skype for Business. Há **três opções** para usar uma política de cliente para definir a experiência do cliente.
  
  **Opção 1:** Definir a experiência de cliente do Skype usando uma política global. Observe que a política global se aplica a todos os usuários em sua implantação, mas as políticas de nível de usuário e de site têm precedência sobre a política global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opção 2:** Modificar uma política de cliente existente que você está usando no seu ambiente para incluir a configuração para habilitar a experiência de cliente do Skype. Isso permite que você atribua a experiência de cliente do Skype somente aos usuários que tenham a política existente atribuída:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opção 3:** Crie uma nova política para atribuir a usuários que incluem a configuração para a experiência de cliente do Skype. Primeiro, crie a nova política de cliente e forneça o nome da política como o valor do parâmetro **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Em seguida, atribua a política aos usuários, usando o nome da política (o valor que você usou para o parâmetro **Identity** ) como o valor do parâmetro **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Etapa 3:** Depois de configurar suas políticas de cliente, implante o cliente Skype for Business, compilação 4711,1002 (abril, 2015) ou posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar a experiência de cliente do Lync com o Lync Server 2013 ou o Lync Server 2010 local
<a name="LyncwithLynconprem"> </a>

Esta é a experiência padrão quando o cliente Skype for Business é implantado em uma implantação do Lync Server local. Você não precisa configurar nenhuma política de cliente para usar a experiência de cliente do Lync, mas talvez queira controlar o comportamento da tela de apresentação do cliente. Por padrão, a primeira vez que os usuários iniciam o cliente Skype for Business, a experiência de cliente do Skype é usada e uma notificação é exibida para os usuários que solicitam que eles reiniciem o cliente para obter a experiência de cliente do Lync. Você pode configurar seu ambiente para que a experiência de cliente do Lync seja exibida na primeira vez que os usuários iniciam o cliente, além de desativar o tutorial do cliente modificando o registro do sistema em computadores clientes. Para as etapas que você precisa executar antes de implantar o cliente Skype for Business, consulte um dos seguintes tópicos:
  
- **Lync server 2013**, consulte [Configurar a experiência do cliente com o Skype for Business no Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010** consulte [Configurar a experiência do cliente com o Skype for Business no Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar a experiência de cliente do Lync com o Skype for Business Server no local
<a name="LyncwithSfBServer"> </a>

Siga as etapas nesta seção se você quiser configurar a experiência de cliente do Lync em uma implantação local do Skype for Business Server.
  
Siga as etapas nesta seção se você quiser configurar a experiência de cliente do Skype em uma implantação local. A experiência padrão para o local
  
 **Etapa 1:** Primeiro, implante o Skype for Business Server.
  
 **Etapa 2:** Em seguida, use uma política de cliente para definir a experiência de cliente do Lync com o cliente Skype for Business. Há **três opções** para usar uma política de cliente para definir a experiência do cliente.
  
 **Opção 1:** Definir a experiência do cliente do Lync usando uma política global. Observe que a política global se aplica a todos os usuários em sua implantação, mas as políticas de nível de usuário e de site têm precedência sobre a política global:
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opção 2:** Modificar uma política de cliente existente que você está usando no seu ambiente para incluir a configuração para habilitar a experiência de cliente do Lync. Isso permite que você atribua a experiência de cliente do Lync somente aos usuários que tenham a política existente atribuída:
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opção 3:** Crie uma nova política para atribuir a usuários que incluem a configuração para a experiência de cliente do Lync. Primeiro, crie a nova política de cliente e forneça o nome da política como o valor do parâmetro **Identity** :
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Em seguida, atribua a política aos usuários, usando o nome da política (o valor que você usou para o parâmetro **Identity** ) como o valor do parâmetro **PolicyName** :
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Etapa 3: opcional** -por padrão, a primeira vez que os usuários iniciam o cliente Skype for Business, a experiência de cliente do Skype é usada e uma notificação é exibida para os usuários solicitando que reiniciem o cliente para obter a experiência de cliente do Lync. Você pode configurar seu ambiente para que a experiência de cliente do Lync seja exibida na primeira vez que os usuários iniciam o cliente, além de desativar o tutorial do cliente, modificando o registro do sistema em computadores clientes. Para as etapas que você precisa executar antes de implantar o cliente Skype for Business, consulte [Configurar a experiência do cliente com o Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).
  
 **Etapa 4:** Depois de configurar suas políticas de cliente, implante o cliente Skype for Business, compilação 4711,1002 (abril, 2015) ou posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar a experiência de cliente do Lync com o Skype for Business Online
<a name="LyncwithSfBO"> </a>

Siga as etapas nesta seção se você quiser configurar a experiência do cliente do Lync e usar o Skype for Business online.
  
Se você estiver usando o Skype for Business Online, ainda poderá usar a experiência de cliente do Lync com o cliente Skype for Business em sua organização usando o PowerShell remoto para configurar políticas de cliente. Há **três opções** para usar uma política de cliente para definir a experiência do cliente. Observe que os nomes de política e parâmetro são diferentes das configurações que você usa para configurar a experiência do cliente quando estiver usando o Skype for Business ou o Lync Server no local.
  
 **Opção 1:** Definir a experiência do cliente do Lync usando uma política global. Observe que as políticas de cliente e de site aplicadas aos usuários terão precedência sobre a política global.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opção 2:** Modificar uma política de cliente existente que você está usando no seu ambiente para incluir a configuração para habilitar a experiência de cliente do Lync. Isso permite que você atribua a experiência de cliente do Lync somente aos usuários que tenham a política existente atribuída:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opção 3:** Use uma instância de política personalizada que inclua a configuração para a experiência de cliente do Lync.
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Depois de configurar suas políticas de cliente, implante o cliente Skype for Business, compilação 4711,1002 (abril, 2015) ou posterior.
  
Para obter informações detalhadas sobre como configurar a experiência do cliente com o Skype for Business Online, incluindo etapas sobre como controlar a experiência de primeira execução e os scripts do PowerShell que você pode usar para configurar seu ambiente, consulte [alternando entre o Skype for Business e as interfaces de usuário do cliente Lync](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos para ajudá-lo a preparar suas equipes de suporte e seus usuários finais para a atualização
<a name="support"> </a>

Para facilitar para você e sua organização preparar-se para a transição, temos vários recursos adicionais disponíveis para ajudá-lo a planejar, educar e envolver os usuários finais.
  
- [Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Guias de início rápido do Skype for Business (download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [O Lync agora é Skype for Business – Veja o que há de novo](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: guia passo a passo para novos usuários](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Por que vejo o Skype for Business quando estou usando o Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

