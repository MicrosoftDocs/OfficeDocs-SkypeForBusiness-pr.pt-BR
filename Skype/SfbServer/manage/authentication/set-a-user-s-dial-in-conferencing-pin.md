---
title: Defina o PIN de conferência discado de um usuário em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Resumo: defina o PIN de conferência discado de um usuário para Skype for Business Server.'
ms.openlocfilehash: 45ee99a0e9ab1b10c429fae470e528ffdd2c3326
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856678"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Defina o PIN de conferência discado de um usuário em Skype for Business Server
 
**Resumo:** Defina o PIN de conferência discado de um usuário para Skype for Business Server.
  
Para ingressar em uma conferência discada como um usuário autenticado, um usuário Skype for Business Server com credenciais do Active Directory Domain Services (AD DS) requer um PIN (número de identificação pessoal). Se um usuário esquecer o PIN de conferência discada ou não tiver definido o PIN usando Skype for Business Server, você poderá definir o PIN do usuário a partir Skype for Business Server Painel de Controle. Você pode gerar automaticamente o PIN ou criá-lo manualmente.
  
> [!NOTE]
> Características específicas do PIN, como seu tamanho mínimo, podem ser configuradas como uma política. Além da política global, é possível configurar uma política de PIN para sites ou usuários individuais. 
  
### <a name="to-set-a-users-pin"></a>Para definir o PIN de um usuário

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Utilize um dos métodos a seguir para localizar um usuário:
    
   - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
   - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.
    
5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa à sua consulta, clique em **Adicionar filtro**. 
  
   e. Clique em **Localizar**.
    
    > [!NOTE]
    > Se o PIN estiver bloqueado, você deverá desbloquear o PIN para que possa defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e em **Desbloquear PIN**. 
  
6. Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Definir PIN**.
    
7. Na caixa de diálogo **Definir PIN**, siga um destes procedimentos:
    
   - Para permitir Skype for Business Server gerar o PIN do usuário, selecione Gerar automaticamente um **PIN válido** (o padrão).
    
   - Para criar seu próprio PIN, clique em **Inserir manualmente um PIN específico**, clique na caixa de texto e digite um PIN na caixa de texto que atenda aos requisitos de PIN especificados nas configurações de política de PIN.
    
8. Clique em **OK**.
    
9. Em **Definir PIN**, siga um destes procedimentos: 
    
   - Marque a caixa de seleção **Mostrar PIN** para ver o PIN e copie o PIN e comunique-o ao usuário usando o método preferencial da sua organização.
    
   - Clique em **Abrir meu aplicativo de email para enviar o novo PIN para o usuário** para enviar o novo PIN por email. Se o Microsoft Office Outlook for seu cliente de email, o PIN será copiado automaticamente para uma nova mensagem de email. Se você usar um cliente de email diferente, marque a caixa de seleção **Mostrar PIN** para ver o PIN e copiá-lo em sua mensagem de email.
    
10. Clique em **Fechar**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Atribuir um PIN de usuário usando Windows PowerShell cmdlets

Você também pode atribuir números PIN usando o cmdlet Set-CsClientPin. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Para atribuir automaticamente um número de PIN a um usuário

O comando a seguir atribui um número PIN ao usuário Ken Myer. Como o parâmetro Pin não está incluído, Skype for Business Server gerará e atribuirá automaticamente o número pin.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Para atribuir um número de PIN específico a um usuário

Esse comando utiliza o parâmetro PIN para atribuir o número de PIN 121989 ao usuário Ken Myer.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsClientPin.](/powershell/module/skype/set-csclientpin?view=skype-ps)
