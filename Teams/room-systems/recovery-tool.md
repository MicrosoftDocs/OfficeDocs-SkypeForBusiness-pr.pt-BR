---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte.
ms.openlocfilehash: 04fd6b4b0786cffb4f1bb050a7b0bbdac8e2e653
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573644"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar a ferramenta de recuperação das Salas do Microsoft Teams
 
Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte. Você usaria essa ferramenta quando o console de salas do Microsoft Teams mostra um erro de "configuração do sistema desatualizada".
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Pré-requisitos

Baixe o [pacote de instalação das salas do Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) mais recente e extraia-o em um joystick de memória USB ou compartilhamento de rede acessível ao dispositivo de salas do Microsoft Teams.

Você também pode precisar instalar o [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Verificar versão do Windows 

1. Faça logon em uma conta de administrador acessando **configurações> configuração do Windows> entrar no Microsoft Teams Inscreva-se** no dispositivo de salas do Microsoft Teams. Essa opção traz para a tela de login.
2. Conecte-se a uma conta de administrador, a conta `admin` de administrador padrão `sfb`que está usando a senha.
3. Clique no menu iniciar e digite `winver.exe` na caixa de pesquisa e clique em **executar comando* no resultado.
4. Anote o número após ' version ' na segunda linha do painel de informações.

>[!NOTE]
>Se a versão mostrada for 1607 ou anterior, siga as etapas nas etapas <a href="#Windows-up">atualizar o Windows antes da recuperação</a> antes de <a href="#Perform">realizar uma</a> etapa de recuperação. Se a versão mostrada for maior que 1607, siga apenas as etapas em <a href="#Perform">executar uma recuperação</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Atualizar o Windows antes da recuperação (se necessário)

1. Enquanto estiver conectado como um usuário administrador, inicie um prompt elevado do PowerShell.
2. Executar o comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Execute o Windows Update e instale a atualização para o Windows 1709.
4. Depois que a atualização para o 1709 for concluída, conecte-se novamente à conta de administrador e instale o [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). A atualização pode ser feita a partir do link ou usando o Windows Update.
5. Como uma etapa opcional, instale as atualizações adicionais disponíveis no Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Executar uma recuperação

1. Entre na conta de administrador em seu dispositivo de salas do Microsoft Teams e inicie um prompt de comando elevado.
2. Verifique o dispositivo de salas Microsoft Teams que você pode acessar o `RecoveryTool.ps1` arquivo, que está incluído nos arquivos extraídos do pacote de instalação de salas do Microsoft Teams. O kit pode ser encontrado no compartilhamento de rede ou na unidade USB usada ao preparar pré-requisitos.
3. Execute o comando `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.
4. Quando solicitado pela opção `1:"Repair System"`de seleção de script.
5. Após a conclusão, reinicie o dispositivo de salas do Microsoft Teams. Ele reiniciará novamente automaticamente e a recuperação será completada na segunda vez.



<a name="See"> </a>  
## <a name="see-also"></a>Confira também
 
[Suporte às Salas do Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
