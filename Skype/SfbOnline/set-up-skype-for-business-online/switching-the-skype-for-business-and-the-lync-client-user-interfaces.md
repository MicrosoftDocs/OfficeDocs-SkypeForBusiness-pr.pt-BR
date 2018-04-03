---
title: Alternando entre as interfaces do usuário do cliente Skype for Business e do cliente Lync
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 5458fb4838ce2e7847a49caa31f92d2151e2a382
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Alternando entre as interfaces do usuário do cliente Skype for Business e do cliente Lync

Para as organizações que têm o Skype for Business Online, você pode usar o PowerShell Remoto no Office 365 para permitir que os usuários do Skype for Business utilizem a interface do usuário do cliente Skype for Business ou do cliente Skype for Business (Lync). Na configuração padrão, os usuários devem utilizar a interface do cliente Skype for Business. Se você preferir usar a experiência do cliente Lync, é possível gerenciar o comportamento do cliente primeiro lançamento para exibir a interface de usuário do Lync seguindo as etapas neste tópico.
  
> [!NOTE]
> [!OBSERVAçãO] A experiência do cliente Lync 2013 não é uma opção para as versões do cliente Skype for Business 2016. Antes de tentar configurar seu ambiente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ela não começa com o número 16. Por exemplo: 16.x.x.x. 
  
> [!TIP]
> [!DICA] Se desejar alternar facilmente a interface do usuário sem seguir as etapas manuais, consulte o [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/?LinkId=532431) para obter um script PowerShell e tornar essa tarefa mais fácil.
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>Alternando a interface do Skype for Business para os usuários

O módulo Windows PowerShell para Skype for Business Online permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, aceito somente em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft, em [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Para obter outras informações, consulte [Configurando o computador para gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=534539).
  
> [!IMPORTANT]
> [!IMPORTANTE] A configuração da política  _Global_ para alternar a interface do usuário não será aplicada aos usuários que já têm uma política personalizada aplicada. Para alterar a interface, você precisará executar o seguinte para cada usuário que tiver uma política personalizada aplicada:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> [!CUIDADO] A política  _ClientPolicyEnableSkypeUI_ substituirá a configuração de política existente do usuário.
  
Para permitir que todos os usuários de sua organização utilizem o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Se definir a política corretamente, você verá:
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Para permitir que todos os usuários de sua organização utilizem o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte: 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Se definir a política corretamente, você verá:
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Para permitir que um único usuário de sua organização utilize o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

Se definir a política corretamente, você verá:
  
![Skype for Business Online - Habilitar interface do usuário](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
Para permitir que um único usuário de sua organização utilize o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

Se definir a política corretamente, você verá:
  
![Skype for Business Online - Interface do Usuário Desabilitada](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
Para permitir que vários usuários de sua organização utilizem o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Para permitir que vários usuários de sua organização utilizem o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte:
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Para permitir que um grupo de usuários de sua organização utilize o cliente Skype for Business, abra o PowerShell Remoto e digite o seguinte:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Para permitir que um grupo de usuários de sua organização utilize o cliente Skype for Business (Lync), abra o PowerShell Remoto e digite o seguinte:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  [!OBSERVAçãO]  O nome do usuário é o nome da conta do usuário à qual a política deve ser atribuída. O nome da conta do usuário pode ser inserido em um dos seguintes formatos:>  Endereço SIP do usuário>  Nome UPN do usuário>  Domínio\\nome de usuário do usuário>  Nome para exibição do Active Directory do usuário
  
[Usando o Windows PowerShell para gerenciar o Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>Configurações de política do Skype for Business Online

Esta tabela mostra a experiência do usuário quando a política é aplicada pela primeira aos usuários:
  
|**Configuração da política de Administração**|**Interface do usuário exibida**|
|:-----|:-----|
|A política não está definida. |O usuário continuará a utilizar a interface do cliente Skype for Business.|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|O usuário continuará a utilizar a interface do cliente Skype for Business.|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|O usuário será solicitado a alternar para a interface do cliente Skype for Business (Lync). Ele poderá alternar posteriormente.|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|O usuário utilizará a interface do cliente Skype for Business. |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|O usuário será solicitado para alternar para o Skype para interface de usuário do cliente de negócios (Lync). No futuro, o administrador poderá alterar a configuração de modo que o usuário alterne para a interface do cliente Skype for Business. |
   
Esta tabela mostra a experiência do usuário quando a política é alterada:
  
|**Configuração da política de Administração**|**Interface do usuário do Skype for Business (Lync)**|**Interface do usuário do Skype for Business**|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|O usuário será solicitado a alternar para a interface do cliente Skype for Business.  <br/> |O usuário continuará a utilizar a interface do cliente Skype for Business.  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|O usuário continuará a usar o Skype para interface de negócios (Lync).  <br/> |O usuário será solicitado para alternar para o Skype para interface de usuário do cliente de negócios (Lync).  <br/> |
|A política não está definida.  <br/> |Os usuários verão o Skype para interface de usuário do cliente de negócios (Lync) nunca se a diretiva não estiver definida. Eles sempre utilizarão a interface do cliente Skype for Business.  <br/> |O usuário continuará a utilizar a interface do cliente Skype for Business.  <br/> |
   
Esta tabela mostra todas as políticas personalizadas online disponíveis. Novas políticas foram criadas para dar flexibilidade aos administradores na retenção da antiga política personalizada durante a troca entre os sinalizadores EnableSkypeUI. Use os cmdlets acima para conceder uma das políticas abaixo para seus usuários.
  
|**Nome da política**|**EnableSkypeUI**|
|:-----|:-----|
```ClientPolicyDefaultPhoto```||
```ClientPolicyDefaultPhotoDisableSkypeUI``` |Falsa|
```ClientPolicyNoIMURL```||
```ClientPolicyNoIMURLDisableSkypeUI``` |Falsa|
```ClientPolicyNoIMURLPhoto```||
```ClientPolicyNoIMURLPhotoDisableSkypeUI``` |Falsa|
```ClientPolicyNoSaveIMNoArchivingI```||
```ClientPolicyNoSaveIMNoArchivingDisableSkypeUI``` |Falsa|
```ClientPolicyNoSaveIMNoArchivingNoIMURL```||
```ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI``` |Falsa|
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto``` ||
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI```|Falsa|
```ClientPolicyNoSaveIMNoArchivingPhoto```||
```ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI``` |Falsa|

   
Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
  
- [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>Comportamentos do cliente na primeira inicialização

Por padrão, quando os usuários iniciar Skype para negócios pela primeira vez, eles verão sempre o Skype para interface de usuário de negócios – mesmo se você selecionou a experiência do cliente Lync, definindo a política de cliente para a experiência do cliente Lync (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) conforme descrito anteriormente. Após alguns minutos, os usuários serão solicitados a mudar para o modo Lync.
  
Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após ser atualizado:
  
1. Siga as etapas descritas anteriormente neste tópico e confirme se a política do cliente está configurada para desabilitar a interface do usuário do Skype for Business.
    
2. Atualize o registro do sistema no computador do usuário. Você deve fazer isso antes que os novos usuários iniciem o cliente Skype for Business, e deve fazer isso apenas uma vez. Para obter informações sobre como criar um Objeto de Política de Grupo para atualizar o registro em um computador que ingressou no domínio, consulte a seção posterior no tópico.
    
    Na chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**, crie um novo valor **Binário**.
    
    O **Nome do valor** deve ser **EnableSkypeUI**, e os **Dados do valor** devem ser configurados para **00 00 00 00**.
    
    A chave deve ser semelhante a esta:
    
    [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab" = DWORD: 00000001
    
    "CanShareOneNoteInCollab" = DWORD: 00000001
    
    "CanAppShareInCollab" = DWORD: 00000001
    
    "EnableSkypeUI" = hex: 00, 00, 00,00
    
A interface do usuário do Lync será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar a exibição do tutorial da tela de boas-vindas

Quando os usuários abrem o Skype para o cliente de negócios, o comportamento padrão é exibir uma tela de boas-vindas que inclui *7 dicas rápidas para a maioria das pessoas pedir*. Você pode desativar a exibição da tela de boas-vindas, mais ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:
  
Na chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, crie um novo valor **DWORD (32 bits)**. O **Nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **Dados do valor** devem ser configurados para **1**.
  
A chave deve ser semelhante a esta:
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a>Desativar o tutorial do cliente

Se você não quiser que os usuários acessem o tutorial, desative o tutorial do cliente com o seguinte valor do Registro:
  
Na chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**, crie um novo valor **DWORD (32 bits)**. O **Nome do valor** deve ser **TutorialFeatureEnabled**, e os **Dados do valor** devem ser configurados para **0**.
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Você pode reativar o tutorial configurando os **Dados de valor** para **1**.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Criar um Objeto de Política de Grupo para modificar o Registro em um computador que ingressou no domínio

A atualização do Registro para exibir a experiência de cliente do Lync na primeira vez que o usuário inicia o cliente Skype for Business deve ser realizada somente uma vez. Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, será preciso definir o objeto para um novo valor em vez de atualizar os Dados de valor. Quando o GPO for aplicado, se não existir um novo valor, o GPO o criará e configurará os Dados de valor para 0.
  
O procedimento a seguir descreve como modificar o Registro para que a experiência de cliente do Lync seja exibida na primeira vez que o usuário iniciar o Skype for Business. Você também pode usar este procedimento para atualizar o Registro para desativar o tutorial da tela de boas-vindas conforme descrito anteriormente.
  
 **Para criar o GPO**
  
1. Inicie o **Console de Gerenciamento de Política de Grupo**.
    
    Para obter informações sobre como usar o Console de Gerenciamento de Política de Grupo, consulte [Console de Gerenciamento de Política de Grupo](https://go.microsoft.com/fwlink/?LinkId=532759).
    
2. Clique com o botão direito do mouse no nó **Objetos de Política de Grupo** e selecione **Novo** no menu.
    
3. Na caixa de diálogo **Novo GPO**, digite o nome do GPO, por exemplo, MakeLyncDefaultUI, e clique em **OK**.
    
4. Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.
    
5. No **Editor de Gerenciamento de Política de Grupo**, expanda **Configuração do Usuário**, **Preferências**, **Configurações do Windows** e selecione o nó **Registro**.
    
6. Clique com o botão direito do mouse no nó **Registro** e selecione **Novo** > **Item do Registro**.
    
7. Na caixa de diálogo **Novas Propriedades do Registro**, atualize o seguinte:
    
|**Campo**|**Valor a selecionar ou inserir**|
|:-----|:-----|
|**Ação** <br/> |**Criar** <br/> |
|**Hive** <br/> | HKEY_CURRENT_USER <br/> |
|**Caminho da Chave** <br/> |Software\\Microsoft\\Office\\Lync  <br/> |
|**Nome do valor** <br/> |EnableSkypeUI  <br/> |
|**Tipo de valor** <br/> |REG_BINARY  <br/> |
|**Dados do valor** <br/> |00000000  <br/> |
   
Clique em **OK** para salvar as alterações e feche o GPO.
    
Em seguida, você precisará vincular o GPO que você criou para o grupo de usuários ao qual a política será atribuída, como uma UO.
  
 **Usar o GPO para atribuir a política**
  
1. No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na UO para a qual você deseja atribuir a política e selecione **Vincular a um GPO existente**.
    
2. Na caixa de diálogo **Selecionar GPO**, selecione o GPO que você criou e clique em **OK**.
    
3. No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:
    
    **gpupdate /target:user**
    
    A mensagem "Atualizando a política..." é exibida enquanto o GPO é aplicado. Ao concluir, a mensagem "A atualização da Política de Usuário foi concluída com êxito" é exibida.
    
4. No prompt de comando, digite o seguinte comando:
    
    **gpresult /r**
    
    Você deve ver "Objetos de Política de Grupo Atribuídos" com o nome do GPO criado exibido abaixo.
    
Você também pode verificar se o GPO atualizou com êxito o Registro no computador de um usuário examinando o Registro. Abra o Editor do Registro e navegue até a chave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Se o GPO atualizou o Registro com êxito, você verá um valor chamado EnableSkypeUI com o valor 0.
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 