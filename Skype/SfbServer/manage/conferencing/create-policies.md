---
title: Criar políticas de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Resumo: saiba como criar políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: 078c80af0304c796bd3935200764a9ce6e13585b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991886"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a>Criar políticas de conferência no Skype for Business Server
 
**Resumo:** Saiba como criar políticas de conferência no Skype for Business Server.
  
Você pode criar políticas de conferência usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Criar políticas de conferência usando o painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, em seguida, clique em **Política de Conferência**.
    
4. Clique em **Novo** e execute uma das seguintes ações:
    
   - Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de Conferências**, em **Nome**, digite um nome descritivo para a política.
    
   - Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecionar um Site**, digite todo ou parte do nome do site para o qual você deseja criar uma política. Na lista de sites, clique no site que você deseja e clique em **OK**.
    
     > [!NOTE]
     > O nome do site se tornará o nome da política de conferências e não poderá ser alterado. 
  
5. Em **Descrição**, digite uma descrição para a política.
    
6. Em **Política do Organizador**, em **Tamanho máximo de reuniões**, digite o número máximo de usuários que deseja permitir em uma reunião. Por padrão, o tamanho máximo de reuniões é 250.
    
7. Para impedir que usuários convidem usuários anônimos para reuniões, desmarque a opção **Permitir que participantes convidem usuários anônimos**. Usuários anônimos são usuários que não têm credenciais nos serviços de domínio do Active Directory da sua organização e quem, portanto, não são autenticados. Por padrão, usuários podem convidar usuários anônimos para reuniões.
    
8. Em **Gravação**, execute um dos seguintes procedimentos:
    
   - Para impedir que os participantes gravem reuniões, clique em **Nenhuma**. Essa é a configuração padrão.
    
   - Para permitir que os participantes gravem reuniões, clique em **Habilitar gravação**.
    
9. Para permitir que participantes externos gravem reuniões, selecione a opção **Permitir que participantes federados e anônimos gravem**. O padrão é impedir que participantes externos gravem reuniões.
    
10. Em **Áudio/vídeo**, execute um dos seguintes procedimentos:
    
    - Para impedir o uso de áudio e vídeo, clique em **Nenhum**.
    
    - Para permitir o uso de áudio mas não de vídeo, clique em **Habilitar áudio IP**.
    
    - Para permitir o uso de áudio e vídeo, clique em **Habilitar áudio/vídeo IP**. Esta é a configuração padrão.
    
11. Se você optar por permitir o uso de áudio em **Áudio/vídeo**, execute o seguinte procedimento:
    
    - Para impedir os usuários de entrar em uma reunião discando, desmarque a opção **Habilitar conferências discadas PSTN**. Por padrão, os usuários podem discar para reuniões usando a rede telefônica pública comutada (PSTN).
    
    - Se for permitido que usuários disquem para reuniões e você desejar permitir que usuários não autenticados (anônimos) entrem em reuniões usando dial out phoning, selecione a opção **Permitir que participantes anônimos façam chamadas**. Com o dial-out phoning, o servidor de conferências faz uma chamada para o usuário e o usuário atende o telefone para e entrar na reunião. Por padrão, usuários anônimos não podem entrar em uma reunião usando dial-out phoning.
    
12. Se você escolher permitir o uso de vídeo em **Áudio/vídeo**, marque **Permitir vários fluxos de vídeo**.
    
13. Em **Colaboração de Dados**, execute um dos seguintes procedimentos:
    
    - Para impedir a colaboração de dados, clique em **Nenhuma**.
    
    - Para permitir a colaboração de dados, clique em **Habilitar colaboração de dados**. Essa é a configuração padrão.
    
14. Se você optar por permitir a colaboração de dados em **Colaboração de Dados**, execute o seguinte procedimento:
    
    - Para impedir downloads externos, desmarque a opção **Permitir que participantes federados e anônimos façam download de conteúdo**. Por padrão, usuários externos não podem fazer download de conteúdo.
    
    - Para impedir transferências de arquivos, desmarque a opção **Permitir que participantes transfiram arquivos**. Por padrão, os usuários podem transferir arquivos.
    
    - Para impedir o uso de anotações, desmarque a opção **Habilitar anotações**. Para usar as anotações em apresentações do PowerPoint compartilhadas, marque **Habilitar anotações do PowerPoint**. Por padrão, as anotações são permitidas.
    
    - Para impedir o uso de votações, desmarque a opção **Habilitar votações**. Por padrão, votações são permitidas.
    
15. Em **Compartilhamento de aplicativos**, execute um dos seguintes procedimentos:
    
    - Para impedir o uso do compartilhamento de aplicativos, clique em **Desabilitar compartilhamento de aplicativos**.
    
    - Para permitir o uso de compartilhamento de aplicativos, clique em **Habilitar o compartilhamento de aplicativos**. Esta é a configuração padrão.
    
16. Se você optar por permitir o compartilhamento de aplicativos em **Compartilhamento de aplicativos**, execute o seguinte procedimento:
    
    - Para impedir que participantes de reuniões assumam o controle do compartilhamento de aplicativos, desmarque a opção **Permitir que participantes assumam o controle**. Por padrão, os participantes podem assumir o controle do compartilhamento de aplicativos.
    
    - Se você optar por permitir que os participantes de uma reunião assumam o controle do compartilhamento de aplicativos, selecione a opção **Permitir que participantes federados e anônimos assumam o controle** para permitir que usuários externos assumam o controle do compartilhamento de aplicativos. Por padrão, usuários externos não podem assumir o controle do compartilhamento de aplicativos.
    
17. Sob **Política do participante**, execute um dos seguintes procedimentos:
    
    - Para impedir ambos, compartilhamento de aplicativos e de área de trabalho, clique em **Desabilitar compartilhamento de aplicativos e da área de trabalho**.
    
    - Para permitir o compartilhamento de aplicativos mas não da área de trabalho, clique em **Habilitar compartilhamento de aplicativos**.
    
    - Para permitir ambos, compartilhamento de aplicativos e da área de trabalho, clique em **Habilitar compartilhamento de aplicativos e da área de trabalho**. Esta é a configuração padrão.
    
18. Para impedir transferências de arquivo ponto a ponto, desmarque a opção **Habilitar transferências de arquivos ponto a ponto**. Por padrão, as transferências de arquivo ponto a ponto são permitidas.
    
19. Para permitir a gravação ponto a ponto, selecione a opção **Habilitar gravação ponto a ponto**. Por padrão, a gravação ponto a ponto não está habilitada.
    
20. Para permitir que os participantes façam parte de vários fluxos de vídeo, marque a caixa de seleção **Habilitar os participantes a se unir a vários fluxos de vídeo**. Por padrão, vários fluxos de vídeo são permitidos.
    
21. Clique em **Confirmar**.
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Criar políticas de conferência usando o Shell de gerenciamento do Skype for Business Server

Para criar políticas de conferência, use o cmdlet **New-Cs ConferencingPolicy**.
  
O exemplo a seguir cria uma nova política de conferência com o SalesConferencingPolicy de identidade. Essa política utilizará todos os valores padrão em uma política de conferência, exceto um: MaxMeetingSize. Nesse exemplo, o tamanho máximo de uma reunião será definido como 50, em vez do valor padrão de 250.:
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

Para obter mais informações, incluindo uma descrição completa da sintaxe e lista de parâmetros, veja [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).
  

