---
title: Configurar um console de Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar e configurar o console das Salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: 4caa2677eea01ecc96e426692b536aec8563c473
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117569"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurar um console de Salas do Microsoft Teams

Este artigo descreve como configurar o console do Microsoft Teams Rooms e seus periféricos.
  
Você só deve executar essas etapas se as contas necessárias do Microsoft Teams ou do Skype for Business e do Exchange já foram criadas e testadas conforme descrito em [Deploy Microsoft Teams Rooms](rooms-deploy.md). Você precisará do hardware e software descritos nos [requisitos de Salas do Microsoft Teams.](requirements.md) Este tópico inclui as seguintes seções:
  
- [Preparar a mídia de instalação](console.md#Prep_Media)
- [Instalar um certificado ca privado no console](console.md#Certs)
- [Instalar o Windows 10 e o aplicativo de console do Microsoft Teams Rooms](console.md#Reimage)
- [Configuração inicial do console](console.md#Initial)
- [Lista de verificação de implantação do Microsoft Teams Rooms](console.md#Checklist)

> [!NOTE]
> As Salas do Microsoft Teams só funcionarão em um ambiente do Microsoft Teams ou skype for Business configurado corretamente, onde as contas de dispositivo são configuradas corretamente, conforme descrito em [Deploy Microsoft Teams Rooms](rooms-deploy.md).
  
## <a name="prepare-the-installation-media"></a>Preparar a mídia de instalação
<a name="Prep_Media"> </a>

A instalação do aplicativo de console salas do Microsoft Teams requer um dispositivo de armazenamento USB com pelo menos 32 GB de capacidade. Não deve haver outros arquivos no dispositivo; todos os arquivos existentes no armazenamento USB serão perdidos.
  
> [!NOTE]
> A falha ao criar a mídia de instalação do Microsoft Teams Rooms de acordo com essas instruções provavelmente resultará em comportamento inesperado.

> [!NOTE]
> O processo a seguir é para criar mídia de instalação para imagem de novos dispositivos do Microsoft Teams Rooms. Dispositivos existentes, por padrão, são atualizados automaticamente do Windows Update e da Windows Store.

> [!IMPORTANT]
> A máquina do Windows 10 usada para criar a mídia de instalação do Microsoft Teams Rooms deve estar na mesma versão ou posterior do Windows que a mídia de instalação de destino.
  
1. Baixe o [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).
2. Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.
3. Siga as instruções do script para criar um disco de configuração USB de Salas do Microsoft Teams.


> [!TIP]
> Sempre que o script CreateSrsMedia.ps1 for iniciado, a saída de tela incluirá o nome de um arquivo de log ou transcrição da sessão. Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte. 

O CreateSrsMedia.ps1 script automatiza as seguintes tarefas:

1. Baixe o instalador MSI mais recente para Salas do Microsoft Teams.
2. Determine a com build do Windows que o usuário deve fornecer. As versões lançadas mais recentemente podem ou não ser testadas e suportadas para uso com dispositivos Microsoft Teams Rooms.
3. Baixe os componentes de suporte necessários.
4. Montar os componentes necessários na mídia de instalação.

Uma versão específica do Windows 10 é necessária e essa versão só está disponível para clientes de licenciamento por volume.  Você pode obter uma cópia do Centro de [Serviços de Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/)

Quando terminar, remova o disco USB do computador e prossiga para [Instalar o Windows 10 e](console.md#Reimage)o aplicativo de console salas do Microsoft Teams.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar o Windows 10 e o aplicativo de console do Microsoft Teams Rooms
<a name="Reimage"> </a>

Agora você precisa aplicar a mídia de instalação criada. O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar apenas o aplicativo de console salas do Microsoft Teams.

1. Se o dispositivo de destino for instalado em um dock (por exemplo, um Surface Pro), desconecte-o do dock.

2. Verifique se o dispositivo de destino não está conectado à rede.

3. Verifique se o dispositivo de destino está conectado à energia ac.

4. Conecte seu disco de configuração USB ao dispositivo de destino.

5. Inicializar no disco de configuração USB. Consulte as instruções do fabricante. Se o dispositivo de destino for um Surface Pro, use as etapas a seguir para inicializar no disco de configuração USB:

    a. Pressione e continue a segurar o botão de volume para baixo (-).

    b. Pressione e solte o botão de energia.

    c. Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).

8. O sistema será desligado depois que a instalação for concluída.
    
Depois que o sistema for desligado, é seguro remover o disco de configuração USB. Neste ponto, você pode colocar o dispositivo de destino em seu encaixe (se estiver usando um produto baseado em dock), anexar os periféricos necessários para sua sala de reunião e se conectar à rede. Consulte as instruções do fabricante.

> [!NOTE]
> As atualizações de software para Salas do Microsoft Teams são baixadas automaticamente da Microsoft Store para Empresas. Consulte [Pré-requisitos da Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business) e Educação para verificar se o console de sala poderá acessar a loja e a atualização automática.  

### <a name="selecting-a-language"></a>Selecionar um idioma 

Na Atualização do Criador, você precisará usar o script ApplyCurrentRegionAndLanguage.ps1 em cenários em que a seleção implícita de idioma não fornece ao usuário o idioma real do aplicativo que deseja (por exemplo, eles querem que o aplicativo de console seja usado em francês, mas está chegando em inglês).
  
> [!NOTE]
> As instruções a seguir funcionam apenas para consoles criados usando a Atualização do Windows Creator. Os sistemas herdado/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não poderão usar essas instruções, mas também não devem sofrer com o problema inicial que exige essa intervenção manual (a Edição de Aniversário permite que você escolha explicitamente o idioma do aplicativo como parte da instalação).
  
### <a name="to-apply-your-desired-language"></a>Para aplicar o idioma desejado

1. Mude para o modo de Administrador.
    
2. Selecione o menu Iniciar.
    
3. Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.
    
4. Selecione **Idioma &amp; de hora**.
    
5. Selecione **Idioma &amp; de região**.
    
6. Selecione **Adicionar um idioma**.
    
7. Selecione o idioma que deseja adicionar.
    
8. Selecione o idioma que você acabou de adicionar à lista "Idiomas".
    
9. Selecione **Definir como padrão**.
    
10. Para idiomas que deseja remover:
    
    a. Selecione o idioma que deseja remover.
    
    b. Selecione **Remover**.
    
11. Inicie um prompt de comandos com privilégios elevados.
    
12. Execute o seguinte comando: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Reinicie o sistema.
    
Seu idioma desejado agora é aplicado ao console de Salas do Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuração inicial do console
<a name="Initial"> </a>

Depois que o Windows for instalado, o aplicativo de console do Microsoft Teams Rooms entrará em seu processo inicial de Instalação quando for iniciado em seguida ou se a opção /reboot foi escolhida.
  
1. A tela Conta de Usuário é exibida. Insira o endereço de entrada do Skype (user@domain formato) da conta de sala a ser usada com o console.
    
2. Digite a senha para a conta da sala e digite-a novamente para verificar.
    
3. Em "Configurar Domínio", de definir o FQDN para o Skype for Business Server. Se o domínio SIP do Skype for Business for diferente do domínio exchange do usuário, insira o domínio exchange neste campo.
    
4. Click **Next**.
    
5. Selecione os dispositivos indicados na tela Recursos e clique em **Próximo**. O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado. Os dispositivos para selecionar são:
    
   - Microfone para conferência: o microfone padrão para a sala de conferência.
    
   - Alto-falante para conferência: o alto-falante padrão para conferência  
    
   - Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.
    
     Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.
    
6. Clique em **Concluir**.
    
O aplicativo de console salas do Microsoft Teams deve começar a entrar imediatamente no Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com o Exchange usando essas mesmas credenciais. Para obter detalhes sobre como usar o aplicativo de console, consulte a ajuda salas [do Microsoft Teams.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> As Salas do Microsoft Teams se baseam na presença de hardware de console certificado. Mesmo uma imagem criada corretamente contendo o aplicativo de console do Microsoft Teams Rooms não será inicializada após o procedimento de instalação inicial, a menos que o hardware do console seja detectado. Para soluções baseadas no Surface Pro, o Surface Pro deve estar conectado ao hardware de encaixe que acompanha para passar essa verificação.
  
> [!NOTE]
> Alguns usuários de idiomas que não são do inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial, caso os símbolos não sejam suportados no teclado por toque.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar um certificado ca privado no console
<a name="Certs"> </a>

O console de Salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos que ele se conecta. No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente. Em um caso em que a Autoridade de Certificação é privada, por exemplo, uma implantação local com o Active Directory e a Autoridade de Certificação do Windows, você pode adicionar o certificado ao console das Salas do Microsoft Teams de algumas maneiras:
  
- Você pode ingressar o console no Active Directory e isso adicionará automaticamente os certificados necessários, uma vez que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).
    
- Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes de fazer isso, você deve concluir [a configuração inicial do console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar o certificado manualmente 

1. Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque o console no modo de administração (consulte [Admin mode and device management](rooms-operations.md#AdminMode)).
    
3. Execute o seguinte comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Ingressar em um domínio do Active Directory (Opcional)
<a name="Certs"> </a>

Você pode ingressar nos consoles das Salas do Microsoft Teams no seu domínio. Os consoles de Salas do Microsoft Teams devem ser colocados em uma OU separada das estações de trabalho do computador, pois muitas políticas de estação de trabalho não são compatíveis com salas do Microsoft Teams. Um exemplo comum são as políticas de aplicação de senha que impedirão que as Salas do Microsoft Teams sejam insu operacional automaticamente. Para obter informações sobre o gerenciamento de configurações de GPO, consulte [Manage Microsoft Teams Rooms](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para ingressar as Salas do Microsoft Teams em um domínio

1. Entre no console da conta de administrador (consulte [Admin mode and device management](rooms-operations.md#AdminMode)).
    
2. Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.
    
3. Digite o seguinte comando no Powershell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por exemplo, se seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de Salas do Microsoft Teams sejam em uma OU "Salas do Microsoft Teams" que seja filho de uma OU "Resources", o comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se você quiser renomear o computador ao jun-lo a um domínio, use o sinalizador -NewName seguido pelo novo nome do computador.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Lista de verificação de implantação do Microsoft Teams Rooms
<a name="Checklist"> </a>

Use a seguinte lista de verificação ao fazer uma verificação final de que o console e todos os periféricos estão totalmente configurados:
  
**Configurações do aplicativo**

|||
|:-----|:-----|
|☐  <br/> |O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console  <br/> |
|☐  <br/> |O nome do computador Windows está definido corretamente (útil para administração remota)  <br/> |
|☐  <br/> |A senha da conta do administrador foi definida e verificada  <br/> |
|☐  <br/> |Todas as atualizações de firmware foram aplicadas  <br/> |
   
**Periféricos de áudio/vídeo**

|||
|:-----|:-----|
|☐  <br/> |A versão do firmware do periférico da câmera está correta (se aplicável)  <br/> |
|☐  <br/> |Câmera funcional e posicionada de forma ideal  <br/> |
|☐  <br/> |Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado  <br/> |
|☐  <br/> |Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado  <br/> |
|☐  <br/> |A versão do firmware do periférico de áudio está correta (se aplicável)  <br/> |
|☐  <br/> |Dispositivo de entrada de áudio funcional e posicionado corretamente  <br/> |
|☐  <br/> |Dispositivo de saída de áudio funcional e posicionado corretamente  <br/> |
   
**Encaixe**

|||
|:-----|:-----|
|☐  <br/> |Os cabos estão presos e não estão dobrados  <br/> |
|☐  <br/> |Ingestão de áudio via HDMI funcional  <br/> |
|☐  <br/> |Ingestão de vídeo via HDMI funcional  <br/> |
|☐  <br/> |O encaixe pode girar livremente  <br/> |
|☐  <br/> |O brilho da tela é aceitável para o ambiente  <br/> |
   
## <a name="see-also"></a>Confira também
<a name="Checklist"> </a>

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)