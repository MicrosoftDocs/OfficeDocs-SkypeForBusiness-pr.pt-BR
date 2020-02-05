---
title: Configurar a experiência do cliente com o Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumo: Leia este tópico para saber como configurar a experiência do cliente para usuários do Skype for Business.'
ms.openlocfilehash: 678bda8499ddae61f0cca3b3bbb606283192660b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769074"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurar a experiência do cliente com o Skype for Business 2015
 
**Resumo:** Leia este tópico para saber como configurar a experiência do cliente para os usuários do Skype for Business 2015.
  
O Skype for Business 2015 oferece uma nova experiência de usuário baseada na experiência do produto Skype para consumidores. Além de todos os recursos do Lync, o Skype for Business oferece novos recursos com controles simplificados e ícones conhecidos. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [explorar o Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).
  
O Skype for Business Server é compatível com a nova experiência de cliente do Skype for Business, bem como com a experiência do cliente do Lync. Como administrador, você pode escolher a experiência do cliente preferida para os seus usuários. Por exemplo, talvez você queira implantar a experiência do cliente do Lync até que os usuários em sua organização sejam totalmente treinados na nova experiência do Skype for Business. Ou, se você ainda não tiver atualizado todos os usuários para o Skype for Business Server, talvez queira que todos os usuários tenham a mesma experiência de cliente até que todos sejam atualizados para o novo servidor.
  
> [!IMPORTANT]
> Se a sua organização tiver o Skype for Business Server e o Lync Server implantados, a experiência do cliente padrão será diferente, dependendo das versões do servidor e das configurações da interface do usuário. Quando os usuários iniciarem o Skype for Business pela primeira vez, eles verão sempre a interface do usuário do Skype for Business, mesmo que você tenha selecionado a experiência do cliente do Lync. Após alguns minutos, os usuários são solicitados a alternar para o modo Lync. Para mais informações, consulte **Comportamento do cliente na primeira inicialização**, que será abordado neste tópico.
  
> [!NOTE]
> A experiência do cliente do Lync 2013 não é uma opção para versões do cliente do Skype for Business 2016 ou posterior. Antes de tentar configurar o ambiente do cliente para usar o cliente Lync 2013, verifique a versão do cliente para garantir que ele não comece com o número 16; por exemplo: 16. x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurar experiência do cliente

Você pode especificar a experiência que os clientes na sua organização terão usando o cmdlet **Set-CSClientPolicy** com o parâmetro EnableSkypeUI:
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

onde XdsIdentity refere-se à política Global ou a uma política de local nomeado.
  
O comando a seguir seleciona a experiência do cliente Skype for Business para todos os usuários da sua organização afetados pela política global (Lembre-se de que as políticas específicas do site ou do usuário substituem a política global): 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

O próximo comando seleciona a experiência do cliente do Lync para todos os usuários da sua organização afetados pela política global:
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

O próximo comando seleciona a experiência do cliente Skype for Business para todos os usuários no site de Redmond:
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Se você quiser configurar a experiência do cliente para usuários específicos em sua organização, poderá criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e, em seguida, atribuir a política a usuários específicos usando o cmdlet **Grant-CsClientPolicy** .
  
Por exemplo, o comando a seguir cria uma nova política de cliente, SalesClientUI, que seleciona a experiência do cliente do Skype for Business:
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

A próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de Vendas:
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamentos do cliente na primeira inicialização

Por padrão, quando os usuários iniciam o Skype for Business 2015 pela primeira vez, eles sempre verão a interface do usuário do Skype for Business, mesmo que você tenha selecionado a experiência do cliente do Lync definindo o valor do $False parâmetro EnableSkypeUI como descrito tenha. Após alguns minutos, os usuários serão solicitados a mudar para o modo Lync.
  
Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após ser atualizado:
  
1. Confirme se o valor de `EnableSkypeUI` está definido como $false na política que você está usando, conforme descrito anteriormente.
    
2. Atualize o registro do sistema no computador do usuário. Você deve fazer isso antes que os novos usuários iniciem o cliente Skype for Business, e deve fazer isso apenas uma vez. Para obter informações sobre como criar um Objeto de Política de Grupo para atualizar o registro em um computador que ingressou no domínio, consulte a seção posterior no tópico.
    
    Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, crie um novo valor **Binário**.
    
    O **Nome do valor** deve ser **EnableSkypeUI**, e os **Dados do valor** devem ser configurados para **00 00 00 00**.
    
    A chave deve ser semelhante a esta:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

A interface do usuário do Lync será exibida quando os usuários iniciarem o cliente Skype for Business pela primeira vez.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Tutorial de controle da exibição da tela de boas-vindas

Quando os usuários abrem o cliente Skype for Business, o comportamento padrão é exibir uma tela de boas-vindas que inclua *7 dicas rápidas que a maioria das pessoas pede*. Você pode desativar a exibição da tela de boas-vindas, mais ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:
  
Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **Dados do valor** devem ser definidos como **1**.
  
A chave resultante deve se parecer com a seguinte:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Desativar o tutorial do cliente

Se não quiser que seus usuários tenham acesso ao tutorial, você pode desligar o tutorial do cliente com o seguinte valor de Registro:
  
Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **TutorialFeatureEnabled**, e os **Dados do valor** devem ser definidos como **0**.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

Você pode ativar o tutorial novamente definindo os **Dados do valor** para **1**.
  
## <a name="default-client-behaviors"></a>Comportamentos padrão do cliente

Se a sua organização tiver o Skype for Business Server e o Lync Server implantados, a experiência do cliente será diferente, dependendo das versões do servidor e da configuração da interface do usuário do Skype. A seguinte tabela mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:
  

|**Versão do servidor**|**Configuração EnableSkypeUI**|**Experiência do cliente**|
|:-----|:-----|:-----|
|Skype for Business Server |Padrão  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Verdadeiro  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Falso  <br/> |O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Padrão  <br/> |O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Verdadeiro  <br/> |Skype for Business  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Falso  <br/> |O usuário pediu alternar para o modo Lync (o usuário pode alternar para o Skype for Business mais tarde, se você alterar a configuração da interface do usuário para $true)  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sem patches)  <br/> |Padrão  <br/> |O usuário pediu alternar para o modo Lync (o usuário não pode mudar para o Skype for Business mais tarde)  <br/> |
   
A tabela a seguir mostra a experiência do cliente quando o administrador muda a configuração inicial para a experiência da interface do usuário do Skype:
  

|**Versão do servidor**|**Configuração EnableSkypeUI**|**Interface do usuário do cliente = Lync**|**Interface do usuário do cliente = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |Verdadeiro  <br/> |O usuário pediu que mudar para o Skype for Business  <br/> |Skype for Business  <br/> |
|Skype for Business Server |Falso  <br/> |Modo Lync  <br/> |O usuário pediu alternar para o modo Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Verdadeiro  <br/> |O usuário pediu que mudar para o Skype for Business  <br/> |Skype for Business  <br/> |
|Lync Server 2010 ou Lync Server 2013 (com patches corretos)  <br/> |Falso  <br/> |Modo Lync  <br/> |O usuário pediu alternar para o modo Lync  <br/> |
|Lync Server 2010 ou Lync Server 2013 (sem patches)  <br/> |Padrão  <br/> |Modo Lync (não é possível mudar para o Skype for Business)  <br/> |Modo Lync (não é possível mudar para o Skype for Business)  <br/> |
   
As versões de patch necessárias para gerenciar a configuração do cliente Skype for Business são:
  
- Lync Server 2010-atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010. Para obter informações, consulte [atualizações para o Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013. Para obter informações, consulte [atualizações para o Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crie um Objeto de Política de Grupo para modificar o registro em um computador com ingresso no domínio

A atualização do registro para exibir a experiência do cliente do Lync na primeira vez que um usuário iniciar o cliente Skype for Business 2015 deve ser feito apenas uma vez. Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, será preciso definir o objeto para um novo valor em vez de atualizar os Dados de valor. Quando o GPO for aplicado, se não existir um novo valor, o GPO o criará e configurará os Dados de valor para 0. 
  
O procedimento a seguir descreve como modificar o registro para que a experiência do cliente do Lync seja exibida na primeira vez que um usuário iniciar o cliente Skype for Business 2015. Você também pode usar esse procedimento para atualizar o registro para desabilitar o tutorial da tela de boas-vindas, conforme descrito anteriormente.
  
### <a name="to-create-the-gpo"></a>Para criar o GPO

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
   |**Caminho chave** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nome do valor** <br/> |EnableSkypeUI  <br/> |
   |**Tipo de valor** <br/> |REG_BINARY  <br/> |
   |**Dados do valor** <br/> |00000000  <br/> |
   
8. Clique em **OK** para salvar as alterações e feche o GPO.
    
Em seguida, você terá de vincular o GPO criado ao grupo de usuários ao qual você deseja atribuir a política, tal como uma unidade organizacional (OU).
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Para usar o GPO para atribuir a política

1. No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na OU à qual você deseja atribuir a política e, em seguida, selecione **Vincular a um GPO existente**.
    
2. Na caixa de diálogo **Selecionar GPO**, selecione o GPO que você criou e clique em **OK**.
    
3. No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. No prompt de comando, digite o seguinte comando:
    
    **gpresult /r**
    
    Você verá "Objetos Atribuídos da Política de Grupo" com o nome do GPO que você criou exibido abaixo.
    
Você também pode verificar se o GPO atualizou com sucesso o registro no computador de um usuário examinando o registro. Abra o Editor de Registro e navegue até a chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Se o GPO tiver atualizado o registro com sucesso, você verá um valor chamado EnableSkypeUI com o valor de 0.
  

