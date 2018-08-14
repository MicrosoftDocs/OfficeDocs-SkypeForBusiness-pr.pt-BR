---
title: Planejar o Skype para negócios 2015 experiência de cliente para seus usuários
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 'Resumo: Saiba mais sobre o novo Skype para negócios e as etapas que podem ser realizadas para preparar seu ambiente e seus usuários para a atualização, se você estiver usando o Skype para Business Online, Skype para Business Server 2015, Skype para Business Server 2015, Lync Server 2013, ou O Lync Server 2010.'
ms.openlocfilehash: 61f0aad551230c8639a2ea17b612b1aa09bb54df
ms.sourcegitcommit: 47f80b977fa7de3b83a521164f765623bffcf5c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2018
ms.locfileid: "22391745"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>Planejar o Skype para negócios 2015 experiência de cliente para seus usuários
 
**Resumo:** Saiba mais sobre o novo Skype para negócios e as etapas a que seguir para preparar seu ambiente e seus usuários para a atualização, quer você esteja usando o Skype para Business Online, Skype para Business Server 2019, Skype para Business Server 2015, Lync Server 2013 ou do Lync Server 2010.
  
14 de abril de 2015 atualização do Office para o Lync 2013 inclui o novo Skype para interface de usuário de negócios. Essa atualização permite aos administradores controlar a aparência do cliente e escolha se deseja reter a experiência do cliente Lync 2013 ou use o Skype aprimorada para experiência do cliente de negócios. O Skype para o cliente de negócios efetivamente substituído o cliente do Lync 2013 e adicionadas a capacidade dos administradores podem escolher entre a experiência do cliente Lync existente e o novo Skype para a experiência do cliente de negócios. Para obter informações sobre essa atualização, consulte [14 de abril de 2015 atualizar para o Lync 2013 (Skype para negócios) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).
  
Em 12 de maio de 2015, haverá outra atualização mensal do Office que inclui o Skype atualizado para o cliente de negócios. Muitos clientes que não aplicam a atualização irá pegar a 12 de maio de abril atualizar para o Office 2013. As informações neste tópico o ajudarão a preparar sua organização, seu ambiente e seus usuários para a atualização de cliente. Para facilitar a transição para seus usuários e equipes de suporte, utilize as informações neste tópico para decidir qual experiência de cliente você deseja para os usuários e depois fazer as alterações no seu ambiente antes de implantar a atualização de cliente em sua organização.
  
- [What client experience do you want for your users?](user-experience.md#clientexperience)
    
- [Preparar seu ambiente para o cliente do Skype for Business](user-experience.md#usinglync)
    
- [Resources to help you prepare your support teams and your end users for the update](user-experience.md#support)
    
> [!NOTE]
> A experiência do cliente Lync 2013 não é uma opção para Skype para as versões de cliente 2016 de negócios. Antes de tentar configurar seu ambiente do cliente para usar o cliente do Lync 2013, verifique a versão do cliente para garantir que ele não começa com o número de 16; Por exemplo: 16.x.x.x. 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>Qual experiência de cliente você deseja para seus usuários?
<a name="clientexperience"> </a>

Com o novo Skype para cliente corporativos, você pode controlar qual experiência do cliente seus usuários obtêm, Lync ou Skype para negócios. A experiência do cliente padrão depende se você estiver usando o Lync ou Skype para negócios local ou online. Se você estiver usando o Skype para Business Online (Lync Online) hoje com o Office 365 ProPlus, o Office 365 Business Premium ou o Office 2013, o Skype atualizado para o cliente de negócios experiência — inspirada a aparência do Skype — será a experiência do usuário padrão. Se você estiver usando o Lync Server local hoje, a experiência do cliente Lync será o padrão.
  
Você pode configurar qual experiência de cliente seus usuários recebem usando políticas de cliente. Uma diretiva de cliente é um conjunto de definições de configuração que são aplicados aos usuários quando eles fazem login em Lync ou Skype para negócios.
  
### <a name="skype-for-business-client-experience"></a>Experiência de cliente do Skype for Business

Além de todos os recursos do Lync, Skype para negócios fornece novos recursos com controles simplificados e ícones familiares do Skype. Alguns novos recursos do Skype para negócios estão disponíveis apenas com o novo Skype para a experiência do cliente de negócios. Para saber mais sobre os novos recursos do Skype for Business, consulte [Skype descobrir para a empresa](https://go.microsoft.com/fwlink/p/?LinkId=528686).
  
### <a name="lync-client-experience"></a>Experiência de cliente do Lync

A experiência de cliente do Lync é muito semelhante à experiência de cliente do Lync 2013 com a qual seus usuários já estão familiarizados, mas há algumas alterações que convém informar aos usuários. Para ver o que é diferente entre o cliente do Lync 2013 e a experiência do cliente Lync, consulte [por que vejo Skype para negócios ao usar o Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) e os links adicionais neste tópico.
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>Preparar seu ambiente para o cliente do Skype for Business
<a name="usinglync"> </a>

Você terá que fazer algumas coisas para preparar seu ambiente para a atualização de cliente. Antes de começar a fazer quaisquer alterações para configurar a experiência do cliente, você precisará certificar-se de que você estiver usando uma versão do Skype para Business Server ou o Lync Server que suporta as configurações de diretiva de cliente.
  
Depois de confirmar que você está usando uma versão do Skype para Business Server ou o Lync Server que suporta as configurações de diretiva para controlar a experiência do cliente, você precisará definir as configurações de diretiva em seu ambiente. As etapas específicas que precisam ser seguidas dependem da versão do Skype para Business Server ou o Lync Server que você está usando e se os usuários estão no local ou online. 
  
Você vai querer fazer essas alterações antes da atualização do cliente é entregue para seus usuários, de forma que você pode controlar a experiência do cliente na primeira vez em que iniciarem o Skype para o cliente de negócios. As tabelas a seguir indica as etapas necessárias para configurar seu ambiente para a experiência do cliente desejada para seus usuários.
  
|**Implantação**|**Experiência de cliente do Skype for Business**|**Experiência de cliente do Lync**|
|:-----|:-----|:-----|
|Skype for Business Online  <br/> |Não há etapas adicionais para implantar a compilação do cliente 4711.1002 (abril de 2015) ou posterior.  <br/> |[Usar a experiência de cliente do Lync com o Skype for Business Online](user-experience.md#LyncwithSfBO) <br/> |
|Skype for Business Server 2015  <br/> |Não há etapas adicionais para implantar a compilação do cliente 4711.1002 (abril de 2015) ou posterior.  <br/> |[Usar a experiência de cliente do Lync com o Skype for Business Server no local](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 e Lync Server 2010  <br/> |[Usar a experiência do cliente Skype com o Lync Server 2013 ou o Lync Server 2010 no local](user-experience.md#SkypewithLynconprem) <br/> |[Usar a experiência do cliente Lync com o Lync Server 2013 ou o Lync Server 2010 no local](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar a experiência do cliente Skype com o Lync Server 2013 ou o Lync Server 2010 no local
<a name="SkypewithLynconprem"> </a>

Siga as etapas nesta seção se você quiser configurar a experiência de cliente do Skype em uma implantação local. A experiência padrão para o local
  
 **Etapa 1:** Primeiro, verifique se que você estiver executando uma versão do Lync Server que suporta as configurações de diretiva de cliente.
  
- **Lync Server 2013** - você deve estar executando o de 2014 dezembro atualização cumulativa (5.0.8308.857) para o Lync Server 2013 ou uma atualização posterior. Para obter informações, consulte [atualizações do Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
- **Lync Server 2010** - você deve estar executando o de 2015 fevereiro atualização cumulativa (4.0.7577.710) para o Lync Server 2010 ou uma atualização posterior. Para obter informações, consulte [atualizações do Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).
    
 **Etapa 2:** Em seguida, use uma diretiva de cliente para definir a experiência do cliente do Skype com o Skype para o cliente de negócios. Há **3 opções** para usar uma política de cliente para definir a experiência de cliente.
  
 **Opção 1:** defina a experiência de cliente do Skype usando uma política global. Observe que a política global se aplica a todos os usuários na sua implantação, mas as políticas de nível de usuário e site têm precedência sobre a política global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **Opção 2:** modifique uma política de cliente existente que você esteja usando no seu ambiente para incluir a configuração para permitir a experiência de cliente do Skype. Isso permite que você atribua a experiência de cliente do Skype apenas aos usuários que têm a política existente atribuída:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **Opção 3:** crie uma nova política para atribuir aos usuários que inclua a configuração para a experiência de cliente do Skype. Primeiro, crie a nova política de cliente e forneça o nome da política como um valor do parâmetro **Identity**:
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

Em seguida, atribua a política aos usuários, utilizando o nome dela (o valor usado para o parâmetro **Identity**) como o valor do parâmetro **PolicyName**:
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **Etapa 3:** Depois que você configurou suas políticas de cliente, implante o Skype para cliente corporativos, compilação 4711.1002 (abril de 2015) ou posterior.
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>Usar a experiência do cliente Lync com o Lync Server 2013 ou o Lync Server 2010 no local
<a name="LyncwithLynconprem"> </a>

Isso é a experiência padrão quando o Skype para o cliente de negócios é implantado em uma implantação do Lync Server no local. Você não precisa configurar nenhuma política de cliente para usar a experiência de cliente do Lync, mas talvez queira controlar o primeiro comportamento de execução do cliente. Por padrão, os primeira vez que os usuários iniciarem o Skype para cliente corporativos, a experiência do cliente Skype é usada e uma notificação será exibida aos usuários que solicita que eles reinicie o cliente para fazer a experiência do cliente Lync. É possível configurar seu ambiente para que a experiência de cliente do Lync seja exibida na primeira vez que os usuários iniciarem o cliente, bem como quando desativarem o tutorial de cliente modificando o Registro do sistema nos computadores cliente. Para conhecer as etapas, você precisará executar antes de implantar o Skype para cliente corporativos, consulte um dos seguintes tópicos:
  
- **Lync Server 2013**, consulte [Configurar o cliente de experiência com Skype for Business no Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync Server 2010** consulte [Configurar o cliente de experiência com Skype for Business no Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>Usar a experiência de cliente do Lync com o Skype for Business Server no local
<a name="LyncwithSfBServer"> </a>

Siga as etapas desta seção se você deseja configurar a experiência do cliente Lync no Skype local para a implantação de negócios Server 2015.
  
Siga as etapas nesta seção se você quiser configurar a experiência de cliente do Skype em uma implantação local. A experiência padrão para o local
  
 **Etapa 1:** Primeiro, implante Skype para Business Server 2015.
  
 **Etapa 2:** Em seguida, use uma diretiva de cliente para definir a experiência do cliente do Lync com o Skype para o cliente de negócios. Há **3 opções** para usar uma política de cliente para definir a experiência de cliente.
  
 **Opção 1:** defina a experiência de cliente do Lync usando uma política global. Observe que a política global se aplica a todos os usuários na sua implantação, mas as políticas de nível de usuário e site têm precedência sobre a política global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **Opção 2:** modifique uma política de cliente existente que você esteja usando no seu ambiente para incluir a configuração para permitir a experiência de cliente do Lync. Isso permite que você atribua a experiência de cliente do Lync apenas aos usuários que têm a política existente atribuída:
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **Opção 3:** crie uma nova política para atribuir aos usuários que inclua a configuração para a experiência de cliente do Lync. Primeiro, crie a nova política de cliente e forneça o nome da política como um valor do parâmetro **Identity**:
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

Em seguida, atribua a política aos usuários, utilizando o nome dela (o valor usado para o parâmetro **Identity**) como o valor do parâmetro **PolicyName**:
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **Etapa 3: opcional** - por padrão, os primeira vez que os usuários iniciarem o Skype para cliente corporativos, a experiência do cliente Skype é usada e uma notificação será exibida aos usuários solicitando que eles para reiniciar o cliente para fazer a experiência do cliente Lync. Você pode configurar seu ambiente para que a experiência de cliente do Lync seja exibida na primeira vez que os usuários iniciarem o cliente, bem como quando desativarem o tutorial de cliente, modificando o Registro do sistema nos computadores cliente. Para [Configurar o cliente de experiência com Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md), consulte as etapas que precisam ser executadas antes de implantar o Skype para o cliente de negócios.
  
 **Etapa 4:** Depois que você configurou suas políticas de cliente, implante o Skype para cliente corporativos, compilação 4711.1002 (abril de 2015) ou posterior.
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>Usar a experiência de cliente do Lync com o Skype for Business Online
<a name="LyncwithSfBO"> </a>

Siga as etapas desta seção se você deseja configurar a experiência do cliente Lync e estiver usando o Skype para negócios Online.
  
Se você estiver usando o Skype para Business Online, você pode ainda usar a experiência do cliente Lync com o Skype para o cliente de negócios em sua organização usando o PowerShell remoto para configurar políticas de cliente. Há **3 opções** para usar uma política de cliente para definir a experiência de cliente. Observe que os nomes de política e o parâmetro são diferentes das configurações usadas para configurar a experiência do cliente quando você estiver usando o Skype para negócios ou do Lync Server no local.
  
 **Opção 1:** Define a experiência do cliente Lync utilizando-se uma política Global. Observe que as políticas de site e de cliente aplicadas a usuários terão precedência sobre uma política Global.
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opção 2:** modifique uma política de cliente existente que você esteja usando no seu ambiente para incluir a configuração para permitir a experiência de cliente do Lync. Isso permite que você atribua a experiência de cliente do Lync apenas aos usuários que têm a política existente atribuída:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **Opção 3:** Use uma instância de política personalizada que inclui a configuração para a experiência do cliente Lync.
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

Depois que você configurou suas políticas de cliente, implante o Skype para cliente corporativos, compilação 4711.1002 (abril de 2015) ou posterior.
  
Para obter informações detalhadas sobre como configurar o cliente de experiência com Skype para negócios Online, incluindo etapas sobre como controlar a primeira experiência de execução e scripts do PowerShell que você pode usar para configurar seu ambiente, consulte [Alternando entre o Skype para as interfaces de usuário de cliente do Lync e de negócios](https://aka.ms/SfBOUI).
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>Recursos para ajudá-lo a preparar suas equipes de suporte e seus usuários finais para a atualização
<a name="support"> </a>

Para tornar facilitam para você e para sua organização a se preparar para a transição, temos muitos recursos adicionais disponíveis para ajudá-lo a planejar, instruir e entre em contato com os usuários finais.
  
- [Vídeo: Apresentando o Skype para negócios](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [Skype para guias de início rápido de negócios (Download)](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Agora, o Lync é Skype para negócios — consulte What's new](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [Skype for Business: um guia passo a passo para novos usuários](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [Por que vejo Skype para negócios ao usar o Lync?](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

