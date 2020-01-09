---
title: Definir o PIN de conferência discada de um usuário no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Resumo: define o PIN de conferência discada de um usuário para o Skype for Business Server.'
ms.openlocfilehash: 83d1aae54d6e8be4f31b5bd27b6a568d6d88db1e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992278"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Definir o PIN de conferência discada de um usuário no Skype for Business Server
 
**Resumo:** Definir o PIN de conferência discada de um usuário para o Skype for Business Server.
  
Para ingressar em uma conferência discada como um usuário autenticado, um usuário do Skype for Business Server com as credenciais dos serviços de domínio Active Directory (AD DS) requer um PIN (número de identificação pessoal). Se um usuário esquecer o PIN de conferência discada ou não tiver definido o PIN usando o Skype for Business Server, você poderá definir o PIN do usuário no painel de controle do Skype for Business Server. Você pode gerar automaticamente o PIN ou criá-lo manualmente.
  
> [!NOTE]
> Características específicas do PIN, como seu tamanho mínimo, podem ser configuradas como uma política. Além da política global, é possível configurar uma política de PIN para sites ou usuários individuais. 
  
### <a name="to-set-a-users-pin"></a>Para definir o PIN de um usuário

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
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
  
   vocálico. Clique em **Localizar**.
    
    > [!NOTE]
    > Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**. 
  
6. Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Definir PIN**.
    
7. Na caixa de diálogo **Definir PIN**, siga um destes procedimentos:
    
   - Para permitir que o Skype for Business Server gere o PIN do usuário, selecione **gerar automaticamente um PIN válido** (o padrão).
    
   - Para criar seu próprio PIN, clique em **Inserir manualmente um PIN específico**, clique na caixa de texto e digite um PIN na caixa de texto que atenda aos requisitos de PIN especificados nas configurações de política de PIN.
    
8. Clique em **OK**.
    
9. Em **Definir PIN**, siga um destes procedimentos: 
    
   - Marque a caixa de seleção **Mostrar PIN** para ver o PIN e copie o PIN e comunique-o ao usuário usando o método preferencial da sua organização.
    
   - Clique em **Abrir meu aplicativo de email para enviar o novo PIN para o usuário** para enviar o novo PIN por email. Se o Microsoft Office Outlook for seu cliente de email, o PIN será copiado automaticamente para uma nova mensagem de email. Se você usar um cliente de email diferente, marque a caixa de seleção **Mostrar PIN** para ver o PIN e copiá-lo em sua mensagem de email.
    
10. Clique em **Fechar**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Atribuir um PIN do usuário usando cmdlets do Windows PowerShell

Você pode atribuir números PIN utilizando o cmdlet Set-CsClientPin. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Para atribuir automaticamente um número PIN a um usuário

O comando a seguir atribui um número PIN ao usuário Ken Myer. Como o parâmetro PIN não está incluído, o Skype for Business Server gerará e atribuirá automaticamente o número do PIN.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Para atribuir um número PIN específico a um usuário

Esse comando utiliza o parâmetro PIN para atribuir o número de PIN 121989 ao usuário Ken Myer.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .
  

