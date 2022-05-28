---
title: Criar uma Salas do Microsoft Teams imagem
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console Salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: d3c4f534fbd5395c7e0cda8e095b5a6d7a2b8def
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761253"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Criar uma Salas do Microsoft Teams imagem

Este artigo descreve como criar uma imagem de Salas do Microsoft Teams para implantação em massa de Salas do Teams.

> [!NOTE]
> As etapas a seguir só devem ser usadas ao criar uma [imagem baseada em WIM para](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) implantação em massa. Se você estiver recuperando dispositivos individuais, entre em contato com o OEM (Fabricante original do equipamento) para obter suporte.

Você só deverá executar essas etapas se as contas Microsoft Teams ou Skype for Business e Exchange necessárias já tiverem sido criadas e testadas conforme descrito em [Implantar Salas do Microsoft Teams](rooms-deploy.md). Você precisará do hardware e do software descritos [Salas do Microsoft Teams requisitos](requirements.md). Este tópico inclui as seguintes seções:
  
- [Preparar a mídia de instalação](console.md#Prep_Media)
- [Instalar um certificado de autoridade de certificação privado no console](console.md#Certs)
- [Instalar Windows 10 e o aplicativo Salas do Microsoft Teams console do Salas do Microsoft Teams](console.md#Reimage)
- [Configuração inicial do console](console.md#Initial)
- [Salas do Microsoft Teams de verificação de implantação](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Preparar a mídia de instalação
<a name="Prep_Media"> </a>

Instalar o aplicativo Salas do Microsoft Teams console requer um dispositivo de armazenamento USB com pelo menos 32 GB de capacidade. Não deve haver outros arquivos no dispositivo; todos os arquivos existentes no armazenamento USB serão perdidos.
  
> [!NOTE]
> A falha ao criar sua Salas do Microsoft Teams de instalação de acordo com essas instruções provavelmente resultará em um comportamento inesperado.

> [!NOTE]
> O processo a seguir é para criar mídia de instalação para criar novas imagens Salas do Microsoft Teams dispositivos. Os dispositivos existentes, por padrão, são atualizados automaticamente Windows Update a Windows Store.

> [!IMPORTANT]
> O Windows 10 usado para criar a mídia de instalação Salas do Microsoft Teams deve estar na mesma versão ou posterior do Windows que a mídia de instalação de destino.
  
1. Baixe o [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).
2. Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.
3. Siga as instruções do script para criar um disco de instalação Salas do Microsoft Teams USB.


> [!TIP]
> Sempre que o CreateSrsMedia.ps1 script for iniciado, a saída da tela incluirá o nome de um arquivo de log ou transcrição para a sessão. Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte. 

O CreateSrsMedia.ps1 script automatiza as seguintes tarefas:

1. Baixe o instalador MSI mais recente para Salas do Microsoft Teams.
2. Determine a compilação Windows que o usuário deve fornecer. As versões lançadas mais recentemente podem ou não ser testadas e com suporte para uso com Salas do Microsoft Teams dispositivos.
3. Baixe os componentes de suporte necessários.
4. Monte os componentes necessários na mídia de instalação.

> [!NOTE]
Uma versão específica do Windows 10 é necessária e essa versão só está disponível para clientes de licenciamento por volume.  Você pode obter uma cópia do Centro de Serviços de [Licenciamento por Volume](https://www.microsoft.com/Licensing/servicecenter/).

Quando terminar, remova o disco USB do computador e vá para [Instalar o Windows 10 e o aplicativo Salas do Microsoft Teams console.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar Windows 10 e o aplicativo Salas do Microsoft Teams console do Salas do Microsoft Teams
<a name="Reimage"> </a>

Agora você precisa aplicar a mídia de instalação que criou. O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar apenas o Salas do Microsoft Teams aplicativo.

1. Se o dispositivo de destino for instalado em um dock (por exemplo, um Surface Pro), desconecte-o do dock.

2. Verifique se o dispositivo de destino não está conectado à rede.

3. Verifique se o dispositivo de destino está conectado à energia AC.

4. Conecte o disco de instalação USB ao dispositivo de destino.

5. Inicialize no disco de instalação do USB. Consulte as instruções do fabricante. Se o dispositivo de destino for um Surface Pro, use as seguintes etapas para inicializar o disco de instalação usb:

    a. Pressione e continue a segurar o botão de volume para baixo (-).

    b. Pressione e solte o botão de energia.

    c. Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).

8. O sistema será desligado depois que a instalação for concluída.
    
Depois que o sistema for desligado, é seguro remover o disco de instalação do USB. Neste ponto, você pode colocar o dispositivo de destino em seu encaixe (se estiver usando um produto baseado em encaixe), anexar os periféricos necessários para sua sala de reunião e conectar-se à rede. Consulte as instruções do fabricante.

> [!NOTE]
> As atualizações de software Salas do Microsoft Teams são baixadas automaticamente do Microsoft Store para Empresas. Consulte [Os pré-requisitos para Microsoft Store para Empresas e Education](/microsoft-store/prerequisites-microsoft-store-for-business) para verificar se o console da sala será capaz de acessar a loja e atualizar automaticamente.  

### <a name="selecting-a-language"></a>Selecionando um idioma 

Na Atualização do Criador, você precisará usar o script do ApplyCurrentRegionAndLanguage.ps1 em cenários em que a seleção implícita de idioma não fornece ao usuário o idioma real do aplicativo desejado (por exemplo, ele deseja que o aplicativo de console venha em francês, mas está chegando em inglês).
  
> [!NOTE]
> As instruções a seguir funcionam apenas para consoles criados usando Windows Atualização do Criador (Windows 10 20H1) ou posterior.
  
### <a name="to-apply-your-desired-language"></a>Para aplicar o idioma desejado

1. Mude para o modo de Administrador.
    
2. Selecione o menu Iniciar.
    
3. Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.
    
4. Selecione **o idioma hora&amp;**.
    
5. Selecione **o idioma**.
    
6. Selecione **Adicionar um idioma**.
    
7. Selecione o idioma que deseja adicionar.
    
8. Instalar recursos de linguagem.
    
9. Não marque Definir como meu idioma Windows exibição.
    
10. Selecione **Instalar**.
    
11. Selecione o idioma que você acabou de adicionar à lista "Idiomas".
    
12. Definir como padrão - Mover seta para cima para definir o padrão

13. Para idiomas que deseja remover:
    
    a. Selecione o idioma que deseja remover.
    
    b. Selecione Remover.

14. Inicie um prompt de comandos com privilégios elevados.

15. Execute o seguinte comando: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. Reinicie o sistema.
    
O idioma desejado agora é aplicado ao Salas do Microsoft Teams console.
## <a name="initial-set-up-of-the-console"></a>Configuração inicial do console
<a name="Initial"> </a>

Depois Windows for instalado, o Salas do Microsoft Teams aplicativo entrará em seu processo de instalação inicial.
  
1. A tela Conta de Usuário é exibida. Insira o endereço de entrada Exchange conta do Recurso do Microsoft user@domain (no formato user@domain) da conta de sala a ser usada com o console.
    
2. Digite a senha para a conta da sala e digite-a novamente para verificar.
   
3. Selecione o modo de reunião Microsoft Teams suporte, somente Skype for Business, ou uma das duas opções de modo misto. Se necessário, habilite a Autenticação Moderna.

4. Selecione **Avançar**.
    
5. Se estiver usando Skype for Business e se o domínio SIP do Skype for Business for diferente do domínio Exchange do usuário, defina o FQDN para o Skype for Business Server na seção Avançado. Se você não estiver usando Skype for Business ou o domínio SIP corresponder ao domínio Exchange, deixe esta seção em branco.
6. Selecione **Avançar**.
    
7. Selecione **Concluir**.
    
O Salas do Microsoft Teams deve entrar no Microsoft Teams ou Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando essas mesmas credenciais. Para obter detalhes sobre como Salas do Teams, consulte a [ajuda Salas do Microsoft Teams segurança](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salas do Microsoft Teams depende da presença de hardware de console certificado. Mesmo uma imagem criada corretamente contendo o aplicativo Salas do Microsoft Teams console não será inicializada após o procedimento de configuração inicial, a menos que o hardware do console seja detectado. Para Surface Pro soluções baseadas em Surface Pro, o Surface Pro deve estar conectado ao hardware de encaixe que o acompanha para passar essa verificação.
  
> [!NOTE]
> Alguns usuários que não são do idioma inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial caso os símbolos não sejam compatíveis com o teclado virtual.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar um certificado de autoridade de certificação privado no console
<a name="Certs"> </a>
> [!NOTE]
> O exemplo a seguir só se aplica se a conexão Salas do Teams ao Skype for Business.

Salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos qual ele se conecta. Em um caso em que a Autoridade de Certificação é privada, por exemplo, uma implantação local com o Active Directory e a Autoridade de Certificação do Windows, você pode adicionar o certificado ao Salas do Microsoft Teams de algumas maneiras:
  
- Você pode ingressar o console no Active Directory e isso adicionará automaticamente os certificados necessários, considerando que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).
    
- Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes de fazer isso, você deve concluir [a configuração inicial do console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar o certificado manualmente 

1. Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque o console no modo de administrador ([consulte Administração e gerenciamento de dispositivo).](rooms-operations.md#AdminMode)
    
3. Execute o seguinte comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Ingressar em um domínio do Active Directory (opcional)
<a name="Certs"> </a>

Você pode ingressar Salas do Microsoft Teams ao seu domínio. Salas do Microsoft Teams deve ser colocado em uma UO separada das estações de trabalho do computador porque muitas políticas de estação de trabalho não são compatíveis com Salas do Microsoft Teams. Um exemplo comum é uma política de imposição de senha que impedirá Salas do Microsoft Teams inicialização automática. Para obter informações sobre o gerenciamento de configurações de GPO, consulte [Gerenciar Salas do Microsoft Teams](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para ingressar Salas do Microsoft Teams a um domínio

1. Entre no console por meio da conta de administrador ([consulte Administração e gerenciamento de dispositivo).](rooms-operations.md#AdminMode)
    
2. Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.
    
3. Digite o seguinte comando no Powershell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

Por exemplo, se o domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que os consoles do Salas do Microsoft Teams esteja em uma UO "Salas do Microsoft Teams" que seja filho de uma UO "Recursos", o comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se você quiser renomear o computador ao ingressá-lo em um domínio, use o sinalizador -NewName seguido pelo novo nome do computador.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Salas do Microsoft Teams de verificação de implantação
<a name="Checklist"> </a>

Use a seguinte lista de verificação ao fazer uma verificação final de que o console e todos os seus periféricos estão totalmente configurados:
  
**Configurações do aplicativo**

|Concluído |Verificar |
|:-----:|:-----|
|☐   |O nome da conta de sala e o número de telefone (se PSTN habilitado) são exibidos corretamente   |
|☐   |O nome do computador Windows está definido corretamente (útil para administração remota)   |
|☐   |A senha da conta do administrador foi definida e verificada   |
|☐   |Todas as atualizações de firmware foram aplicadas   |
   
**Periféricos de áudio/vídeo**

|Concluído |Verificar |
|:-----:|:-----|
|☐   |A versão do firmware do periférico da câmera está correta (se aplicável)   |
|☐   |Câmera funcional e posicionada de forma ideal   |
|☐   |Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado   |
|☐   |Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado   |
|☐   |A versão do firmware do periférico de áudio está correta (se aplicável)   |
|☐   |Dispositivo de entrada de áudio funcional e posicionado corretamente   |
|☐   |Dispositivo de saída de áudio funcional e posicionado corretamente   |

**Console**

|Concluído |Verificar |
|:-----:|:-----|
|☐   |Os cabos estão presos e não estão dobrados   |
|☐   |Ingestão de áudio via HDMI funcional   |
|☐   |Ingestão de vídeo via HDMI funcional   |
|☐   |O console pode girar livremente   |



   
## <a name="see-also"></a>Confira também
<a name="Checklist"> </a>

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
