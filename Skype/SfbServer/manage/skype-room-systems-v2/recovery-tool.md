---
title: Use a ferramenta de recuperação de v2 de sistemas de sala do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: Este artigo discute como usar a ferramenta de recuperação para sistemas de sala Skype v2, que você usaria para trazer um sistema desatualizado para um estado com suporte.
ms.openlocfilehash: 7c7a6188ec1cbd1153c09b768e81789fcffd266e
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a>Use a ferramenta de recuperação de v2 de sistemas de sala do Skype
 
Este artigo discute como usar a ferramenta de recuperação para sistemas de sala Skype v2, que você usaria para trazer um sistema desatualizado para um estado com suporte. Quando o console do Skype sala sistemas v2 mostra um erro "system config desatualizada", você usaria esta ferramenta.
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Pré-requisitos

Baixe o mais recente [pacote de instalação do Skype sala sistemas v2](https://go.microsoft.com/fwlink/?linkid=851168) e extraia-o para um USB memória pente ou compartilhamento de rede acessível ao dispositivo v2 Skype sistemas de sala.

Você também pode precisar instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Verifique se a versão do Windows 

1. Login com uma conta de administrador indo para **Configurações > Configuração do Windows > Admin entrar** do dispositivo v2 Skype sistemas de sala. Essa opção leva a tela de login.
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

1. Entrar com a conta de administrador no seu dispositivo de v2 Skype sistemas de sala e inicie um prompt de comando elevado.
2. Verifique se o Skype sala v2 dispositivos de sistemas que você seja capaz de acessar o `RecoveryTool.ps1` arquivo, que está incluído nos arquivos extraídos do pacote de instalação do Skype sala sistemas v2. O kit pode ser encontrado no compartilhamento de rede ou unidade USB usado durante a preparação de pré-requisitos.
3. Execute o comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4. Quando solicitado, selecione a opção o script `1:"Repair System"`.
5. Após a conclusão, reinicialize o dispositivo de v2 de sistemas de sala Skype. Ela será reinicializar novamente automaticamente e surgirem recuperada totalmente a segunda vez.



<a name="See"> </a>  
## <a name="see-also"></a>Ver também


#### 

[Gerenciar Skype sala v2 de sistemas](skype-room-systems-v2.md)
#### 
