---
title: Criar definições de configuração de reunião no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Resumo: saiba como criar definições de configuração de reunião no Skype for Business Server.'
ms.openlocfilehash: 3d4f986b850b309d50967da9126b8b4eea08a166
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293841"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Criar definições de configuração de reunião no Skype for Business Server
 
**Resumo:** Saiba como criar definições de configuração de reunião no Skype for Business Server.
  
Você pode criar definições de configuração de reunião usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Criar definições de configuração de reunião usando o painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência** e em **Configuração da reunião**.
    
4. Na página **Configuração de reunião**, clique em **Novo** e siga um destes procedimentos:
    
    - Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e, em seguida, clique em **OK**.
    
    - Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e, em seguida, clique em **OK**.
    
5. Para direcionar os participantes que ligam de um PSTN através do lobby, desmarque a caixa de seleção  **Chamadores PSTN ignoram o lobby**. Por padrão, os participantes discando pelo PSTN irão diretamente para a reunião.
    
6. Para configurar quem pode ser um apresentador na reunião, em **Designar como apresentador**, siga um dos procedimentos abaixo:
    
   - Para não permitir que qualquer pessoa além do organizador seja o apresentador, clique em **Nenhum**.
    
   - Para permitir que apenas participantes membros da sua organização sejam apresentadores, clique em **Empresa**. Esta é a configuração padrão.
    
   - Para permitir que qualquer participante seja o apresentador, clique em **Todos**.
    
7. Para que o organizador selecione um tipo de conferência ao programar uma reunião, desmarque a caixa de seleção  **Tipo de conferência atribuída por padrão**. Por padrão, o tipo de conferência é atribuído automaticamente.
    
8. Para evitar que usuários anônimos (não autenticados) sejam aceitos automaticamente, desmarque a caixa de seleção **Aceitar usuários anônimos por padrão**. Por padrão, os usuários anônimos são aceitos automaticamente nas reuniões.
    
9. Para personalizar o convite da reunião enviado para os participantes, faça o seguinte. Observe que o comprimento máximo das URLs e o texto do rodapé padrão é de 1KB. Exceto para a **URL de ajuda**, se você não especificar um valor para as personalizações, elas não serão incluídas na reunião. Se você não incluir uma URL de ajuda personalizada, a URL da ajuda padrão do Skype for Business será exibida no convite. 
    
   - Para personalizar o logotipo exibido no convite da reunião, na **URL do Logotipo**, insira o local do logotipo. O logotipo deve ser uma imagem GIF ou JPG com um tamanho de 188 por 30 pixels. 
    
   - Para personalizar o texto de ajuda exibido no convite da reunião, na **URL de ajuda**, insira o local do texto de ajuda.
    
   - Para personalizar o texto legal exibido no convite da reunião, na **URL do texto legal**, insira o texto legal.
    
   - Para personalizar o texto do rodapé exibido no convite da reunião, em **Texto do rodapé personalizado**, insira o texto.
    
10. Clique em **Confirmar**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Criar definições de configuração de reunião usando o Shell de gerenciamento do Skype for Business Server

Para criar as novas definições de configurações de reunião, use o cmdlet **New-CsMeetingConfiguration**.
  
O comando a seguir cria um novo conjunto de definições de configuração de reunião para o local Redmond:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Como não há parâmetros (além do parâmetro obrigatório Identity) onde especificado no comando anterior, as novas definições de configuração de reunião usarão os valores padrões para todas as suas propriedades.
  
Para criar configurações que usam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro adequados. Por exemplo, para criar um conjunto de reuniões de configuração da reunião que, por padrão, permite todos em uma reunião serem apresentadores a usarem um comando como este:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Os valores de várias propriedades podem ser modificados, incluindo vários parâmetros. Por exemplo, este comando permite que todos em uma reunião serem apresentadores e também força os usuários PSTN a aguardar enquanto são formalmente admitidos na reunião:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Para obter mais informações, incluindo uma lista completa de parâmetros, consulte [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
  

