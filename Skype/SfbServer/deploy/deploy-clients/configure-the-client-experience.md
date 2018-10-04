---
title: Configurar a experiência do cliente com Skype para negócios 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumo: Leia este tópico para saber como configurar a experiência do cliente para Skype para usuários comerciais.'
ms.openlocfilehash: 9e2a7d53788eda36fc18cb9094cde096864ce2ba
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375355"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurar a experiência do cliente com Skype para negócios 2015
 
**Resumo:** Leia este tópico para saber como configurar a experiência do cliente para Skype para usuários corporativos 2015.
  
Skype para negócios 2015 fornece uma nova experiência do usuário que baseia-se na experiência de produto do consumidor do Skype. Além de todos os recursos do Lync, Skype para negócios fornece novos recursos com controles simplificados e ícones familiares. Para obter informações detalhadas sobre a nova experiência do cliente, consulte [Explore Skype para negócios](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype para Business Server suporta a nova Skype para experiência de cliente de negócios, bem como a experiência do cliente Lync. Como administrador, você pode escolher a experiência do cliente preferida para os seus usuários. Por exemplo, você talvez queira implantar a experiência do cliente Lync até que os usuários em sua organização são treinados totalmente o novo Skype para experiência de negócios. Ou, se você ainda não atualizadas todos os usuários para Skype para Business Server, talvez você queira todos os usuários tenham a mesma experiência de cliente até que todos sejam atualizados para o novo servidor.
  
> [!IMPORTANT]
> Se sua organização tem ambas Skype para Business Server e o Lync Server implantado, a experiência do cliente padrão variarão de acordo com as versões de servidor e configurações de interface do usuário. Quando os usuários início Skype para negócios pela primeira vez, sempre eles verão o Skype para interface de usuário de negócios – mesmo se você selecionou a experiência do cliente Lync. Após alguns minutos, os usuários serão solicitados para alternar para modo de Lync. Para mais informações, consulte **Comportamento do cliente na primeira inicialização**, que será abordado neste tópico.
  
> [!NOTE]
> A experiência do cliente Lync 2013 não é uma opção para Skype para as versões de cliente de negócios 2016 ou posterior. Antes de tentar configurar seu ambiente do cliente para usar o cliente do Lync 2013, verifique a versão do cliente para garantir que ele não começa com o número de 16; Por exemplo: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurar experiência do cliente

Você pode especificar a experiência que os clientes na sua organização terão usando o cmdlet **Set-CSClientPolicy** com o parâmetro EnableSkypeUI:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

onde XdsIdentity refere-se à política Global ou a uma política de local nomeado.
  
O comando a seguir seleciona o Skype para a experiência do cliente de negócios para todos os usuários em sua organização afetada pela diretiva Global (Lembre-se de que diretivas específicas do usuário ou site substituem a política Global): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

O próximo comando seleciona a experiência do cliente do Lync para todos os usuários em sua organização afetada pela diretiva Global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

O próximo comando seleciona o Skype para a experiência do cliente de negócios para todos os usuários dentro do site de Redmond:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Se você deseja configurar a experiência do cliente para usuários específicos dentro da sua organização, você pode criar uma nova política de usuário usando o cmdlet **New-CsClientPolicy** e, em seguida, atribuir a política a usuários específicos usando o **Grant-CsClientPolicy** cmdlet.
  
Por exemplo, o comando a seguir cria uma nova diretiva de cliente, SalesClientUI, que seleciona o Skype para a experiência do cliente de negócios:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

A próximo comando atribui a política, SalesClientUI, a todos os membros do departamento de Vendas:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamentos do cliente na primeira inicialização

Por padrão, quando os usuários iniciar Skype para negócios 2015 pela primeira vez, eles verão sempre o Skype para interface de usuário de negócios – mesmo se você selecionou a experiência do cliente Lync, definindo o valor do parâmetro EnableSkypeUI para $False, conforme descrito anteriormente. Após alguns minutos, os usuários serão solicitados a mudar para o modo Lync.
  
Se você quiser exibir a interface do usuário do Lync quando os usuários iniciarem o cliente Skype for Business pela primeira vez, siga estas etapas antes de o cliente ser iniciado pela primeira vez após ser atualizado:
  
1. Confirme se o valor da `EnableSkypeUI` estiver definida como $False na política que você está usando, conforme descrito anteriormente.
    
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
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar a exibição do tutorial da tela de boas-vindas

Quando os usuários abrem o Skype para o cliente de negócios, o comportamento padrão é exibir uma tela de boas-vindas que inclui *7 dicas rápidas para a maioria das pessoas pedir*. Você pode desativar a exibição da tela de boas-vindas, mais ainda permitir que os usuários acessem o tutorial adicionando o seguinte valor do Registro no computador cliente:
  
Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **IsBasicTutorialSeenByUser**, e os **Dados do valor** devem ser definidos como **1**.
  
A chave deve ser semelhante a esta:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Desativar o tutorial do cliente

Se você não quiser que os usuários acessem o tutorial, desative o tutorial do cliente com o seguinte valor do Registro:
  
Na chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, crie um novo **Valor de DWORD (32 bits)**. O **Nome do valor** deve ser **TutorialFeatureEnabled**, e os **Dados do valor** devem ser definidos como **0**.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Você pode ativar o tutorial novamente definindo os **Dados do valor** para **1**.
  
## <a name="default-client-behaviors"></a>Comportamentos padrão do cliente

Se sua organização tem ambas Skype para Business Server e o Lync Server implantado, a experiência do cliente variarão de acordo com as versões de servidor e da UI de Skype configuração. A seguinte tabela mostra a experiência inicial do cliente com base na versão do servidor e na configuração da interface do usuário:
  

|**Versão do servidor**|**Configuração EnableSkypeUI**|**Experiência do cliente**|
|:-----|:-----|:-----|
|Skype for Business Server |Padrão  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Verdadeiro  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Falso  <br/> |Usuário é solicitado a alternar para o modo do Lync (usuário pode alternar para Skype para negócios posteriormente se você alterar a configuração de interface do usuário para $true)  <br/> |
|Lync Server 2010 ou o Lync Server 2013 (com patches corretas)  <br/> |Padrão  <br/> |Usuário é solicitado a alternar para o modo do Lync (usuário pode alternar para Skype para negócios posteriormente se você alterar a configuração de interface do usuário para $true)  <br/> |
|Lync Server 2010 ou o Lync Server 2013 (com patches corretas)  <br/> |Verdadeiro  <br/> |Skype for Business  <br/> |
|Lync Server 2010 ou o Lync Server 2013 (com patches corretas)  <br/> |Falso  <br/> |Usuário é solicitado a alternar para o modo do Lync (usuário pode alternar para Skype para negócios posteriormente se você alterar a configuração de interface do usuário para $true)  <br/> |
|Lync Server 2010 ou o Lync Server 2013 (sem patches)  <br/> |Padrão  <br/> |Usuário é solicitado a alternar para o modo do Lync (o usuário não pode alternar para Skype para negócios posterior)  <br/> |
   
A próxima tabela mostra a experiência do cliente quando o administrador altera a configuração inicial para a experiência do Skype UI:
  

|**Versão do servidor**|**Configuração EnableSkypeUI**|**Cliente UI = Lync**|**Interface do usuário do cliente = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |Verdadeiro  <br/> |Usuário é solicitado a alternar para Skype para negócios  <br/> |Skype for Business  <br/> |
|Skype for Business Server |Falso  <br/> |Modo do Lync  <br/> |Usuário é solicitado a alternar para o modo do Lync  <br/> |
|Lync Server 2010 ou o Lync Server 2013 (com patches corretas)  <br/> |Verdadeiro  <br/> |Usuário é solicitado a alternar para Skype para negócios  <br/> |Skype for Business  <br/> |
|Lync Server 2010 ou o Lync Server 2013 (com patches corretas)  <br/> |Falso  <br/> |Modo do Lync  <br/> |Usuário é solicitado a alternar para o modo do Lync  <br/> |
|Lync Server 2010 ou o Lync Server 2013 (sem patches)  <br/> |Padrão  <br/> |Modo do Lync (não é possível alternar para Skype para negócios)  <br/> |Modo do Lync (não é possível alternar para Skype para negócios)  <br/> |
   
As versões de patch necessárias para gerenciar a configuração do Skype para o cliente de negócios são:
  
- O Lync Server 2010 - atualização cumulativa de fevereiro de 2015 (4.0.7577.710) para o Lync Server 2010. Para obter informações, consulte [atualizações do Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - atualização cumulativa de dezembro de 2014 (5.0.8308.857) para o Lync Server 2013. Para obter informações, consulte [atualizações do Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Criar um Objeto de Política de Grupo para modificar o Registro em um computador que ingressou no domínio

A atualização do registro para exibir a experiência do cliente do Lync na primeira vez que um usuário inicia o Skype para negócios 2015 cliente deve ser feita apenas uma vez. Se você usar um Objeto de Política de Grupo (GPO) para atualizar o Registro, será preciso definir o objeto para um novo valor em vez de atualizar os Dados de valor. Quando o GPO for aplicado, se não existir um novo valor, o GPO o criará e configurará os Dados de valor para 0. 
  
O procedimento a seguir descreve como modificar o registro para que a experiência do cliente Lync seja exibida na primeira vez que um usuário inicia o Skype para 2015 de negócios do cliente. Você também pode usar esse procedimento para atualizar o registro para desabilitar o tutorial da tela de boas-vindas, conforme descrito anteriormente.
  
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
    
Em seguida, você precisará vincular o GPO que você criou para o grupo de usuários ao qual a política será atribuída, como uma UO.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Para usar o GPO para atribuir a política

1. No Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse na UO para a qual você deseja atribuir a política e selecione **Vincular a um GPO existente**.
    
2. Na caixa de diálogo **Selecionar GPO**, selecione o GPO que você criou e clique em **OK**.
    
3. No computador do usuário de destino, abra um prompt de comando e digite o seguinte comando:
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. No prompt de comando, digite o seguinte comando:
    
    **gpresult /r**
    
    Você verá "Objetos Atribuídos da Política de Grupo" com o nome do GPO que você criou exibido abaixo.
    
Você também pode verificar se o GPO atualizou com sucesso o registro no computador de um usuário examinando o registro. Abra o Editor de Registro e navegue até a chave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Se o GPO tiver atualizado o registro com sucesso, você verá um valor chamado EnableSkypeUI com o valor de 0.
  

