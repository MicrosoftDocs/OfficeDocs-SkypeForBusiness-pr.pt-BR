---
title: Configurar PIN de conferência discada de um usuário no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Resumo: Defina discada um usuário PIN para Skype para Business Server 2015.'
ms.openlocfilehash: d94df7ff557c9a229fd5f049ca10f9c1e7f22407
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server-2015"></a>Configurar PIN de conferência discada de um usuário no Skype for Business Server 2015
 
**Resumo:** Defina discada um usuário PIN para Skype para Business Server 2015.
  
Para ingressar na conferência discada como usuário autenticado, um Skype para usuário Business Server 2015 com credenciais do Active Directory Domain Services (AD DS) requer um número de identificação pessoal (PIN). Se um usuário esquece a conferência discada PIN ou não definiu o PIN usando Skype para Business Server 2015, você pode definir o PIN do usuário do Skype para painel de controle do servidor de negócios. Você pode gerar automaticamente o PIN ou criá-lo manualmente.
  
> [!NOTE]
> Características específicas do PIN, como seu tamanho mínimo, podem ser configuradas como uma política. Além da política global, é possível configurar uma política de PIN para sites ou usuários individuais. 
  
### <a name="to-set-a-users-pin"></a>Para definir o PIN de um usuário

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Use um dos seguintes métodos para localizar um usuário:
    
   - Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.
    
   - Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.
    
5. (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**. 
  
   f. Clique em **Localizar**.
    
    > [!NOTE]
    > Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**. 
  
6. Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Definir PIN**.
    
7. Na caixa de diálogo **Definir PIN**, siga um destes procedimentos:
    
   - Para permitir que Skype para o servidor de negócios 2015 gere o PIN do usuário, selecione **Gerar automaticamente um PIN válido** (padrão).
    
   - Para criar seu próprio PIN, clique em **Inserir manualmente um PIN específico**, clique na caixa de texto e digite um PIN na caixa de texto que atenda aos requisitos de PIN especificados nas configurações de política de PIN.
    
8. Clique em **OK**.
    
9. Em **Definir PIN**, siga um destes procedimentos: 
    
   - Marque a caixa de seleção **Mostrar PIN** para ver o PIN e copie o PIN e comunique-o ao usuário usando o método preferencial da sua organização.
    
   - Clique em **Abrir meu aplicativo de email para enviar o novo PIN para o usuário** para enviar o novo PIN por email. Se o Microsoft Office Outlook for seu cliente de email, o PIN será copiado automaticamente para uma nova mensagem de email. Se você usar um cliente de email diferente, marque a caixa de seleção **Mostrar PIN** para ver o PIN e copiá-lo em sua mensagem de email.
    
10. Clique em **Fechar**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Atribuindo um PIN de usuário usando Cmdlets do Windows PowerShell

Você pode atribuir números PIN utilizando o cmdlet Set-CsClientPin. Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Para atribuir automaticamente um número PIN a um usuário

O comando a seguir atribui um número PIN ao usuário Ken Myer. Porque o parâmetro Pin não for incluído, Skype para Business Server irá gerar automaticamente e atribuir o número PIN.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 

  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Para atribuir um número PIN específico a um usuário

Esse comando utiliza o parâmetro PIN para atribuir o número de PIN 121989 ao usuário Ken Myer.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .
  

