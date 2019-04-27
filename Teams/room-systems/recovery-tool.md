---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Este artigo discute como usar a ferramenta de recuperação para salas de equipes da Microsoft, que você usaria para trazer um sistema desatualizado para um estado com suporte.
ms.openlocfilehash: 9580a94c96b7982a3030ccc0435be8e05f7c4a25
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362555"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usar a ferramenta de recuperação das Salas do Microsoft Teams
 
Este artigo discute como usar a ferramenta de recuperação para salas de equipes da Microsoft, que você usaria para trazer um sistema desatualizado para um estado com suporte. Quando o console de salas de equipes da Microsoft mostra um erro "system config desatualizada", você usaria esta ferramenta.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Pré-requisitos

Baixe o mais recente [pacote de instalação de salas de equipes da Microsoft](https://go.microsoft.com/fwlink/?linkid=851168) e extraia-o para um USB memória pente ou compartilhamento de rede acessível para o dispositivo de salas de equipes da Microsoft.

Você também pode precisar instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Verifique se a versão do Windows 

1. Login com uma conta de administrador, indo para **Settings> Windows Setting> Admin entrar** do dispositivo Microsoft equipes salas. Essa opção leva a tela de login.
2. Conta de entrada em uma conta de administrador, o administrador padrão que está sendo `admin` com a senha `sfb`.
3. Clique no menu Iniciar e digite `winver.exe` na caixa Pesquisar e clique em **Comando executar* no resultado.
4. Anote o número após 'Versão' na segunda linha do painel informações.

>[!NOTE]
>Se a versão mostrada for 1607 ou anterior, siga as etapas nas etapas <a href="#Windows-up">Windows Update antes de recuperação</a> antes de proceding para as etapas de <a href="#Perform">executar uma recuperação</a> . Se a versão mostrada for maior que 1607, siga somente as etapas em <a href="#Perform">Perform uma recuperação</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Atualizar o Windows antes de recuperação (se necessário)

1. Enquanto ainda logado como um usuário admin, inicie um prompt elevado do Powershell.
2. Execute o comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Execute o Windows Update e instalar a atualização para Windows 1709.
4. Após a atualização para 1709 está entrada completa que voltou ao conta de administrador e instala [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). A atualização pode ser feita no link ou usando o Windows Update.
5. Como uma etapa opcional, instale quaisquer atualizações adicionais disponíveis do Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Executar uma recuperação

1. Entrar com a conta de administrador no seu dispositivo de salas de equipes da Microsoft e inicie um prompt de comando elevado.
2. Verificar do dispositivo salas de equipes da Microsoft se você é capaz de acessar o `RecoveryTool.ps1` arquivo, que está incluído nos arquivos extraídos do pacote de instalação do Microsoft equipes salas. O kit pode ser encontrado no compartilhamento de rede ou unidade USB usado durante a preparação de pré-requisitos.
3. Execute o comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4. Quando solicitado, selecione a opção o script `1:"Repair System"`.
5. Após a conclusão, reinicialize o dispositivo de salas de equipes da Microsoft. Ela será reinicializar novamente automaticamente e surgirem recuperada totalmente a segunda vez.



<a name="See"> </a>  
## <a name="see-also"></a>Confira também
 
[Suporte às Salas do Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)