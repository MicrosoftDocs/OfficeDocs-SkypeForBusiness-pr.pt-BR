---
title: Configurar a experiência do cliente com o Skype for Business 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumo: Leia este tópico para saber como configurar a experiência do cliente para usuários do Skype for Business.'
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805951"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurar a experiência do cliente com o Skype for Business 2015
 
**Resumo:** Leia este tópico para saber como configurar a experiência do cliente para usuários do Skype for Business 2015.
  
O Skype for Business 2015 oferece uma nova experiência de usuário baseada na experiência de produto do consumidor do Skype. Além de todos os recursos do Lync, o Skype for Business fornece novos recursos com controles simplificados e ícones familiares. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Explorar o Skype for Business.](https://go.microsoft.com/fwlink/?LinkId=529022)
  
O Skype for Business Server dá suporte à nova experiência de cliente do Skype for Business, bem como à experiência de cliente do Lync. Como administrador, você pode escolher a experiência de cliente preferencial para seus usuários. Por exemplo, talvez você queira implantar a experiência de cliente do Lync até que os usuários em sua organização sejam totalmente treinados na nova experiência do Skype for Business. Ou, se você ainda não tiver atualizado todos os usuários para o Skype for Business Server, talvez queira que todos os usuários tenham a mesma experiência de cliente até que todos sejam atualizados para o novo servidor.
  
> [!IMPORTANT]
> Se a sua organização tiver o Skype for Business Server e o Lync Server implantados, a experiência padrão do cliente será diferente, dependendo das versões do servidor e das configurações da interface do usuário. Quando os usuários iniciarem o Skype for Business pela primeira vez, eles sempre verão a interface do usuário do Skype for Business, mesmo que você tenha selecionado a experiência de cliente do Lync. Após alguns minutos, os usuários são solicitados a alternar para o modo Lync. Para obter mais informações, **consulte o comportamento do cliente de Primeira Iniciação** mais adiante neste tópico.
  
> [!NOTE]
> A experiência de cliente do Lync 2013 não é uma opção para versões de cliente do Skype for Business 2016 ou posterior. Antes de tentar configurar seu ambiente cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ela não comece com o número 16; por exemplo: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurar experiência do cliente

Você pode especificar a experiência do cliente que os usuários em sua organização verão usando o cmdlet **Set-CSClientPolicy** com o parâmetro EnableSkypeUI:
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

onde XdsIdentity refere-se à política Global ou a uma política de site nomeada.
  
O comando a seguir seleciona a experiência de cliente do Skype for Business para todos os usuários em sua organização afetados pela política Global (lembre-se de que as políticas específicas do site ou do usuário substituem a política Global): 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

O próximo comando seleciona a experiência de cliente do Lync para todos os usuários em sua organização afetados pela política Global:
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

O próximo comando seleciona a experiência de cliente do Skype for Business para todos os usuários no site Redmond:
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Se você quiser configurar a experiência do cliente para usuários específicos em sua organização, poderá criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e atribuir a política a usuários específicos usando o cmdlet **Grant-CsClientPolicy.**
  
Por exemplo, o seguinte comando cria uma nova política de cliente, SalesClientUI, que seleciona a experiência de cliente do Skype for Business:
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

O próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de vendas:
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamentos do cliente de primeira iniciação

Por padrão, quando os usuários iniciam o Skype for Business 2015 pela primeira vez, eles sempre veem a interface do usuário do Skype for Business, mesmo que você tenha selecionado a experiência de cliente do Lync definindo o valor do parâmetro EnableSkypeUI como $False conforme descrito anteriormente. Após alguns minutos, os usuários serão solicitados a alternar para o modo Lync.
  
Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após a atualização:
  
1. Confirme se o valor  `EnableSkypeUI` está definido como $False na política que você está usando conforme descrito anteriormente.
    
2. Atualize o Registro do sistema no computador do usuário. Você deve fazer isso antes da primeira vez que os usuários iniciarem o cliente Skype for Business, e você deve fazer isso apenas uma vez. Para obter informações sobre como criar um Objeto de Política de Grupo para atualizar o Registro em um computador ingressado no domínio, consulte a seção mais adiante no tópico.
    
    Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync],** crie um novo **valor Binário.**
    
    O **nome do** valor deve ser  **EnableSkypeUI** e os dados de valor devem ser definidos como **00 00 00 00**.
    
    A chave deve ter a seguinte aparência:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

A interface do usuário do Lync agora será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar a exibição do tutorial da tela de boas-vindas

Quando os usuários abrem o cliente Skype for Business, o comportamento padrão é exibir uma tela de boas-vindas que inclui sete dicas rápidas que a maioria das pessoas *solicita.* Você pode desativar a exibição da tela de boas-vindas, mas ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:
  
Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** crie um novo **valor DWORD (32 bits).** O **nome do** valor deve ser **IsBasicTutorialSeenByUser** e os dados de **valor** devem ser definidos como **1**.
  
A chave deve ter a seguinte aparência:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Desativar o tutorial do cliente

Se você não quiser que os usuários possam acessar o tutorial, poderá desativar o tutorial do cliente com o seguinte valor do Registro:
  
Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** crie um novo **valor DWORD (32 bits).** O **nome value** deve ser **TutorialFeatureEnabled** e os dados **de** valor devem ser definidos como **0**.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

Você pode ativar novamente o tutorial definindo os **dados de valor** como **1**.
  
## <a name="default-client-behaviors"></a>Comportamentos padrão do cliente

Se a sua organização tiver o Skype for Business Server e o Lync Server implantados, a experiência do cliente será diferente dependendo das versões do servidor e da configuração da interface do usuário do Skype. A tabela a seguir mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:
  

|**Versão do servidor**|**Configuração EnableSkypeUI**|**Experiência do cliente**|
|:-----|:-----|:-----|
|Skype para Business Server |Padrão  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Verdadeiro.  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Falso  <br/> |O usuário é solicitado a alternar para o modo Lync (o usuário pode alternar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Padrão  <br/> |O usuário é solicitado a alternar para o modo Lync (o usuário pode alternar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Verdadeiro.  <br/> |Skype for Business  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Falso  <br/> |O usuário é solicitado a alternar para o modo Lync (o usuário pode alternar para o Skype for Business posteriormente se você alterar a configuração da interface do usuário para $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sem patches)  <br/> |Padrão  <br/> |Usuário solicitado a alternar para o modo Lync (o usuário não pode alternar para o Skype for Business posteriormente)  <br/> |
   
A tabela a seguir mostra a experiência do cliente quando o administrador altera a configuração inicial da experiência da interface do usuário do Skype:
  

|**Versão do servidor**|**Configuração EnableSkypeUI**|**Interface do usuário do cliente = Lync**|**Interface do usuário do cliente = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype para Business Server |Verdadeiro.  <br/> |Usuário solicitado a mudar para o Skype for Business  <br/> |Skype for Business  <br/> |
|Skype for Business Server |Falso  <br/> |Modo Lync  <br/> |Usuário solicitado a alternar para o modo Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Verdadeiro.  <br/> |Usuário solicitado a mudar para o Skype for Business  <br/> |Skype for Business  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Falso  <br/> |Modo Lync  <br/> |Usuário solicitado a alternar para o modo Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sem patches)  <br/> |Padrão  <br/> |Modo Lync (não é possível alternar para o Skype for Business)  <br/> |Modo Lync (não é possível alternar para o Skype for Business)  <br/> |
   
As versões de patch necessárias para gerenciar a configuração do cliente Skype for Business são:
  
- Lync Server 2010 - Atualização Cumulativa de fevereiro de 2015 (4.0.7577.710) para Lync Server 2010. Para obter informações, [consulte Atualizações do Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - Atualização Cumulativa de dezembro de 2014 (5.0.8308.857) para Lync Server 2013. Para obter informações, [consulte Atualizações do Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Criar um Objeto de Política de Grupo para modificar o Registro em um computador ingressado no domínio

A atualização do Registro para exibir a experiência de cliente do Lync na primeira vez que um usuário inicia o cliente Skype for Business 2015 deve ser feita apenas uma vez. Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, precisará definir o objeto para criar um novo valor em vez de atualizar os dados value. Quando o GPO é aplicado, se o novo valor não existir, o GPO o criará e definirá os dados de Valor como 0. 
  
O procedimento a seguir descreve como modificar o Registro para que a experiência de cliente do Lync seja exibida na primeira vez que um usuário iniciar o cliente Skype for Business 2015. Você também pode usar esse procedimento para atualizar o Registro e desabilitar o tutorial da tela de boas-vindas, conforme descrito anteriormente.
  
### <a name="to-create-the-gpo"></a>Para criar o GPO

1. Inicie o **console de Gerenciamento de Política de Grupo.**
    
    Para obter informações sobre como usar o Console de Gerenciamento de Política de Grupo, consulte [Console de Gerenciamento de Política de Grupo.](https://go.microsoft.com/fwlink/?LinkId=532759)
    
2. Clique com o botão direito do mouse no nó **Objetos de Política de** Grupo e selecione **Novo** no menu.
    
3. Na caixa **de diálogo Novo GPO,** insira um nome para o GPO, por exemplo,MakeLyncDefaultUI e clique em **OK.**
    
4. Clique com o botão direito do mouse no novo GPO que você acabou de criar e selecione **Editar** no menu.
    
5. No **Editor de Gerenciamento de Política de** Grupo, expanda Configuração do Usuário, expanda  **Preferências,** expanda As Configurações do **Windows** e selecione o **nó do** Registro.
    
6. Clique com o botão direito do mouse no **nó do** Registro e selecione **Novo** Item  >  **do Registro.**
    
7. Na caixa **de diálogo Novas Propriedades do Registro,** atualize o seguinte:
    
   |**Campo**|**Valor a ser selecionado ou insira**|
   |:-----|:-----|
   |**Ação** <br/> |**Create** <br/> |
   |**Hive** <br/> | HKEY_CURRENT_USER <br/> |
   |**Caminho da chave** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Value name** <br/> |EnableSkypeUI  <br/> |
   |**Value type** <br/> |REG_BINARY  <br/> |
   |**Dados de valor** <br/> |00000000  <br/> |
   
8. Clique **em OK** para salvar suas alterações e feche o GPO.
    
Em seguida, você precisará vincular o GPO criado ao grupo de usuários ao que você deseja atribuir a política, como uma UO.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Para usar o GPO para atribuir a política

1. No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na UO à que você deseja atribuir a política e selecione Vincular a um **GPO existente.**
    
2. Na caixa **de diálogo Selecionar GPO,** selecione o GPO que você criou e selecione **OK.**
    
3. No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. No prompt de comando, digite o seguinte comando: 
    
    **gpresult /r**
    
    Você deverá ver "Objetos de Política de Grupo Atribuídos" com o nome do GPO criado exibido abaixo.
    
Você também pode verificar se o GPO atualizou com êxito o Registro no computador de um usuário examinando o Registro. Abra o Editor do Registro e navegue até a **chave [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].** Se o GPO atualizou com êxito o Registro, você verá um valor chamado EnableSkypeUI com um valor 0.
  

