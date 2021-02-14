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
description: Este artigo descreve como configurar e configurar o console de Salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662056"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurar um console de Salas do Microsoft Teams

Este artigo descreve como configurar o console salas do Microsoft Teams e seus periféricos.
  
Você só deverá executar essas etapas se as contas necessárias do Microsoft Teams ou skype for Business e do Exchange já foram criadas e testadas conforme descrito em Implantar Salas do [Microsoft Teams.](rooms-deploy.md) Você precisará do hardware e do software descritos nos [requisitos de Salas do Microsoft Teams.](requirements.md) Este tópico inclui as seguintes seções:
  
- [Preparar a mídia de instalação](console.md#Prep_Media)
- [Instalar um certificado de AC particular no console](console.md#Certs)
- [Instalar o Windows 10 e o aplicativo de console salas do Microsoft Teams](console.md#Reimage)
- [Configuração inicial do console](console.md#Initial)
- [Lista de verificação de implantação de Salas do Microsoft Teams](console.md#Checklist)

> [!NOTE]
> As Salas do Microsoft Teams só funcionarão em um ambiente do Microsoft Teams ou Skype for Business configurado corretamente, conforme descrito em Implantar Salas do [Microsoft Teams.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>Preparar a mídia de instalação
<a name="Prep_Media"> </a>

Instalar o aplicativo de console salas do Microsoft Teams requer um dispositivo de armazenamento USB com pelo menos 32 GB de capacidade. Não deve haver outros arquivos no dispositivo; todos os arquivos existentes no armazenamento USB serão perdidos.
  
> [!NOTE]
> A falha na criação da mídia de instalação das Salas do Microsoft Teams de acordo com essas instruções provavelmente resultará em comportamento inesperado.

> [!NOTE]
> O processo a seguir é para criar mídia de instalação para imagem de novos dispositivos de Salas do Microsoft Teams. Os dispositivos existentes, por padrão, são atualizados automaticamente a partir do Windows Update e da Windows Store.

> [!IMPORTANT]
> O computador windows 10 usado para criar a mídia de instalação do Microsoft Teams Rooms deve estar na mesma versão ou posterior do Windows que a mídia de instalação de destino.
  
1. Baixe o [CreateSrsMedia.ps1 script.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.
3. Siga as instruções do script para criar um disco de configuração USB de Salas do Microsoft Teams.


> [!TIP]
> Sempre que o CreateSrsMedia.ps1 script for iniciado, a saída da tela incluirá o nome de um arquivo de log ou transcrição para a sessão. Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte. 

O CreateSrsMedia.ps1 script automatiza as seguintes tarefas:

1. Baixe o instalador MSI mais recente para Salas do Microsoft Teams.
2. Determine o build do Windows que o usuário deve fornecer. As versões mais recentes podem ou não ser testadas e ter suporte para uso com dispositivos microsoft teams Rooms.
3. Baixe os componentes de suporte necessários.
4. Montar os componentes necessários na mídia de instalação.

Uma versão específica do Windows 10 é necessária, e esta versão só está disponível para clientes de licenciamento por volume.  Você pode obter uma cópia do Centro de Serviços de [Licenciamento por Volume.](https://www.microsoft.com/Licensing/servicecenter/)

Quando terminar, remova o disco USB do computador e prossiga para [Instalar o Windows 10 e](console.md#Reimage)o aplicativo de console salas do Microsoft Teams.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar o Windows 10 e o aplicativo de console salas do Microsoft Teams
<a name="Reimage"> </a>

Agora você precisa aplicar a mídia de configuração que criou. O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar apenas o aplicativo de console salas do Microsoft Teams.

1. Se o dispositivo de destino for instalado em uma base (por exemplo, um Surface Pro), desconecte-o do dock.

2. Verifique se o dispositivo de destino não está conectado à rede.

3. Verifique se o dispositivo de destino está conectado à energia ac.

4. Conecte o disco de configuração USB ao dispositivo de destino.

5. Inicializar no disco de configuração USB. Consulte as instruções do fabricante. Se seu dispositivo de destino for um Surface Pro, use as seguintes etapas para inicializar o disco de configuração USB:

    a. Pressione e continue a manter o botão de volume pressionado (-).

    b. Pressione e solte o botão de energia.

    c. Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).

8. O sistema será desligado assim que a instalação for concluída.
    
Depois que o sistema for desligado, é seguro remover o disco de configuração USB. Neste ponto, você pode colocar o dispositivo de destino no encaixe (se estiver usando um produto baseado em dock), anexar os periféricos necessários para a sala de reunião e conectar-se à rede. Consulte as instruções do fabricante.

> [!NOTE]
> As atualizações de software das Salas do Microsoft Teams são baixadas automaticamente da Microsoft Store para Empresas. Consulte [Pré-requisitos da Microsoft Store](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) para Empresas e Educação para verificar se o console da sala será capaz de acessar a loja e fazer a atualização automática.  

### <a name="selecting-a-language"></a>Selecionando um idioma 

Na Atualização do Criador, você precisará usar o script do ApplyCurrentRegionAndLanguage.ps1 em cenários em que a seleção implícita de idioma não fornece ao usuário o idioma real do aplicativo que deseja (por exemplo, ele quer que o aplicativo de console seja usado em francês, mas está chegando em inglês).
  
> [!NOTE]
> As instruções a seguir funcionam somente para consoles criados usando a Atualização do Windows Creator. Os sistemas herdado/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não poderão usar essas instruções, mas também não deverão ser prejudicados pelo problema inicial que requer essa intervenção manual (a Edição de Aniversário permite que você escolha explicitamente o idioma do aplicativo como parte da configuração).
  
### <a name="to-apply-your-desired-language"></a>Para aplicar o idioma desejado

1. Mude para o modo de Administrador.
    
2. Selecione o menu Iniciar.
    
3. Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.
    
4. Selecione **o idioma &amp; hora.**
    
5. Selecione **o idioma &amp; região.**
    
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
    
O idioma desejado agora é aplicado ao console salas do Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuração inicial do console
<a name="Initial"> </a>

Depois que o Windows estiver instalado, o aplicativo de console salas do Microsoft Teams entrará em seu processo inicial de Configuração quando ele for iniciado em seguida ou se a opção /reinicialização tiver sido escolhida.
  
1. A tela Conta de Usuário é exibida. Insira o endereço de entrada do Skype (user@domain formato) da conta da sala a ser usada com o console.
    
2. Digite a senha para a conta da sala e digite-a novamente para verificar.
    
3. Em "Configurar Domínio", de definir o FQDN para o Skype for Business Server. Se o domínio SIP do Skype for Business for diferente do domínio exchange do usuário, insira o domínio exchange nesse campo.
    
4. Click **Next**.
    
5. Selecione os dispositivos indicados na tela Recursos e clique em **Próximo.** O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado. Os dispositivos para selecionar são:
    
   - Microfone para conferência: o microfone padrão para a sala de conferência.
    
   - Alto-falante para conferência: o alto-falante padrão para conferência  
    
   - Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.
    
     Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.
    
6. Clique em **Concluir**.
    
O aplicativo de console salas do Microsoft Teams deve começar imediatamente a entrar no Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com o Exchange usando essas mesmas credenciais. Para obter detalhes sobre como usar o aplicativo console, consulte a ajuda do [Microsoft Teams Rooms.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> O Microsoft Teams Rooms depende da presença de hardware certificado do console. Mesmo uma imagem criada corretamente contendo o aplicativo de console salas do Microsoft Teams não será inicializada após o procedimento de configuração inicial, a menos que o hardware do console seja detectado. Para soluções baseadas no Surface Pro, o Surface Pro deve estar conectado ao hardware do encaixe que o acompanha para passar nessa verificação.
  
> [!NOTE]
> Alguns usuários que não são do idioma inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial caso não sejam suportados símbolos no teclado virtual.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar um certificado de AC particular no console
<a name="Certs"> </a>

O console salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos que ele se conecta. No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente. Em um caso em que a Autoridade de Certificação é privada, por exemplo, uma implantação local com o Active Directory e a Autoridade de Certificação do Windows, você pode adicionar o certificado ao console salas do Microsoft Teams de algumas maneiras:
  
- Você pode ingressar no console no Active Directory e isso adicionará automaticamente os certificados necessários, uma vez que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).
    
- Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes de fazer isso, você deve concluir [a configuração inicial do console.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>Para instalar o certificado manualmente 

1. Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque o console no modo de administração (consulte [o modo de administração e o gerenciamento de dispositivo).](rooms-operations.md#AdminMode)
    
3. Execute o seguinte comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Ingressar em um domínio do Active Directory (Opcional)
<a name="Certs"> </a>

Você pode ingressar nos consoles das Salas do Microsoft Teams ao seu domínio. Os consoles de Salas do Microsoft Teams devem ser colocados em uma OU separada das estações de trabalho do computador, pois muitas políticas de estação de trabalho não são compatíveis com salas do Microsoft Teams. Um exemplo comum são as políticas de imposição de senha que impedirão que as Salas do Microsoft Teams sejam criadas automaticamente. Para obter informações sobre o gerenciamento de configurações de GPO, consulte [Gerenciar Salas do Microsoft Teams.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para ingressar no Microsoft Teams Rooms em um domínio

1. Entre no console da conta de administrador (consulte [o modo de administração e o gerenciamento de dispositivo).](rooms-operations.md#AdminMode)
    
2. Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.
    
3. Digite o seguinte comando no Powershell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por exemplo, se seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de Salas do Microsoft Teams sejam em uma "Salas do Microsoft Teams" OU que seja filho de um "Recursos" OU, o comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se você quiser renomear o computador ao ingressar nele em um domínio, use o sinalizador -NovoNome seguido do novo nome do computador.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Lista de verificação de implantação de Salas do Microsoft Teams
<a name="Checklist"> </a>

Use a seguinte lista de verificação ao fazer uma verificação final de que o console e todos os seus periféricos estão totalmente configurados:
  
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
