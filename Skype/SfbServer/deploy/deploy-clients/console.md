---
title: Configurar o console do Skype Room Systems versão 2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console do Skype Room Systems versão 2 e seus periféricos.
ms.openlocfilehash: eed37791c73b2deeb9e5f0605dbf1265d9a1d02d
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501022"
---
# <a name="configure-a-skype-room-systems-v2-console"></a>Configurar o console do Skype Room Systems versão 2
 
Este artigo descreve como configurar o console do Skype Room Systems versão 2 e seus periféricos.
  
Você só deve executar estas etapas se o Skype necessária para contas de negócios e do Exchange já foram criado e testado, conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md). Você precisará de hardware e software descritos em [sistemas de sala Skype v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md). Este tópico contém as seguintes seções:
  
- [Preparar a imagem da instalação](console.md#Prep_Image)
    
- [Instalar um certificado de autoridade de certificação privado no dispositivo tablet](console.md#Certs)
    
- [Instalar o Windows 10 e o aplicativo de console do Skype sala sistemas v2](console.md#Reimage)
   
- [Conjunto inicial backup do Console](console.md#Initial)
    
- [Lista de verificação de implantação do Skype sala sistemas v2](console.md#Checklist)
    
> [!NOTE]
> Sistemas de sala Skype v2 exemplos funcionam apenas em um Skype configurada adequadamente para onde as contas de dispositivo estão configuradas corretamente conforme descrito em [implantar sistemas de sala Skype v2](room-systems-v2.md)do ambiente de negócios. 
  
## <a name="prepare-the-installation-image"></a>Preparar a imagem da instalação
<a name="Prep_Image"> </a>

A instalação de sistemas de sala Skype v2 aplicativo em um 4 de Surface Pro ou Surface Pro requer um dispositivo de armazenamento USB com pelo menos 32GB de memória formatado como um disco FAT32. Não deve haver nenhum outro arquivo no dispositivo, todos os arquivos existentes no armazenamento USB serão perdidos. 
  
> [!NOTE]
> Se não for possível criar a imagem do console de acordo com estas instruções, provavelmente ocorrerão comportamentos inesperados. Atualização do Windows 10 Enterprise Data especial (versão 1607) não é mais suportada para criação de imagem do Skype sala sistemas v2. 
  
> [!NOTE]
> Um v2 Skype sala sistemas existentes com Windows 10 Enterprise Data especial Update mudando para sistemas de sala Skype v2 atualização 3 por meio da Windows Store funcionará, mas deve ser feita uma nova instalação, conforme descrito abaixo. 
  
1. Baixe o [MSU para KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).
2. Baixe o [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
3. Coloque o MSU para KB4056892 no mesmo diretório que o script CreateSrsMedia.ps1.
4. Execute o script de CreateSrsMedia.ps1 por um prompt elevado em uma máquina Windows 10.


Siga as instruções do script para criar um disco de instalação do Skype sala sistemas v2 USB. Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e o aplicativo de console do Skype sala sistemas v2 ](console.md#Reimage).
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>Instalar o Windows 10 e o aplicativo de console Skype Room Systems versão 2 
<a name="Reimage"> </a>

Agora, você precisa aplicar a imagem que criou. O tablet será executado como um aparelho e o usuário padrão será definido como executar somente o aplicativo de v2 Skype sistemas de sala. 
  
1. O tablet deve estar conectado a uma fonte de energia. Inicie a partir de um estado totalmente desligado. Se necessário, mantenha pressionado o botão de energia até o tablet desligar.
    
2. Conecte ao tablet o disco de instalação USB.
    
3. Mantenha pressionado o botão de abaixar o volume (-) no tablet. 
    
4. Pressione e solte o botão liga/desliga do tablet.
    
5. Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).
    
6. O sistema será desligado depois que a instalação for concluída.
    
Depois que o sistema foi desligado, é seguro remover o disco de instalação do USB. Nesse momento, você pode colocar o tablet no encaixe e conectar os periféricos necessários para sua sala de reunião. Consulte as instruções do fabricante.
  
 
### <a name="selecting-a-language-in-creators-update"></a>Seleção de idioma no Creator’s Update

Em atualização do criador, você precisará usar o script de ApplyCurrentRegionAndLanguage.ps1 em cenários onde a seleção de idioma implícita não fornecer ao usuário com a linguagem de aplicativos real querem (por exemplo, eles querem que o aplicativo surgir em francês, mas é chegando em inglês).
  
> [!NOTE]
> As instruções a seguir funcionam apenas em dispositivos criados usando o Windows Creator's Update. Os sistemas herdados/disponíveis no mercado que não foram representados adequadamente no novo sistema de provisionamento não poderão usar essas instruções, mas também não deverão apresentar o problema inicial que exigia essa intervenção manual (a edição de aniversário permite que você escolha o idioma do seu aplicativo explicitamente como parte da configuração). 
  
### <a name="to-apply-your-desired-language"></a>Para aplicar o idioma desejado

1. Mude para o modo de Administrador.
    
2. Selecione o menu Iniciar.
    
3. Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.
    
4. Selecione **tempo &amp; idioma**.
    
5. Selecione **região &amp; idioma**.
    
6. Selecione **Adicionar um idioma**.
    
7. Selecione o idioma que deseja adicionar.
    
8. Selecione o idioma que você acabou de adicionar à lista de "Idiomas".
    
9. Selecione **Definir como padrão**.
    
10. Para idiomas que deseja remover:
    
    a. Selecione o idioma que deseja remover.
    
    b. Selecione **Remover**.
    
11. Inicie um prompt de comandos com privilégios elevados.
    
12. Execute o seguinte comando: 
    
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    
13. Reinicie o sistema.
    
O idioma desejado agora é aplicado ao dispositivo v2 Skype sistemas de sala.
## <a name="initial-set-up-of-the-console"></a>Configuração inicial do console 
<a name="Initial"> </a>

Após a instalação do Windows, o aplicativo do Skype sala sistemas v2 entrará em seu processo de instalação inicial, quando ele é iniciado próximo ou se a opção /reboot foi escolhida.
  
1. A tela Conta de Usuário é exibida. Digite o endereço de entrada do Skype (no formato usuário@domínio) da conta da sala a ser usada com o dispositivo.
    
2. Digite a senha para a conta da sala e digite-a novamente para verificar.
    
3. Em "Configurar domínio", defina o FQDN para o Skype para Business Server. Se o Skype para o domínio SIP de negócios for diferente do domínio do Exchange do usuário, insira o domínio do Exchange neste campo.
    
4. Clique em **Avançar**.
    
5. Selecione os dispositivos indicados na tela recursos e clique em **Avançar**. O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado. Os dispositivos para selecionar são:
    
   - Microfone para conferência: o microfone padrão para a sala de conferência.
    
   - Alto-falante para conferência: o alto-falante padrão para conferência  
    
   - Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.
    
    Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.
    
6. Clique em **Concluir**.
    
O aplicativo deve iniciar imediatamente entrando no Skype para Business Server 2015 com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando as mesmas credenciais. Para obter detalhes sobre como usar o aplicativo, consulte a [Ajuda de sistemas de sala Skype versão 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Sistemas de sala Skype v2 depende da presença de hardware do console Certificados (o Logitech SmartDock). Mesmo uma imagem criada corretamente que contém o aplicativo de v2 de sistemas de sala Skype carregado em uma 4 do Surface Pro ou Surface Pro não inicializa passado o procedimento de instalação inicial, a menos que o hardware do console for detectado. 
  
> [!NOTE]
> Talvez os usuários de alguns idiomas diferentes do inglês precisem de um teclado físico conectado ao console durante a instalação inicial, caso alguns símbolos não tenham suporte no teclado virtual. 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a>Instale um certificado de Autoridade de Certificação privado no tablet
<a name="Certs"> </a>

O dispositivo de v2 Skype sala sistemas deve confiar nos certificados usados pelo Skype para servidores de negócios e Exchange a que conecta-se. No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente. No caso em que a autoridade de certificação é particular, por exemplo, uma implantação de local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado ao dispositivo v2 Skype sala sistemas de duas maneiras:
  
- Você pode adicionar o dispositivo ao Active Directory. Assim, os certificados necessários serão automaticamente adicionados, já que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).
    
- Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes disso, você deve concluir a [Configuração inicial do console](console.md#Initial).  
    
### <a name="to-manually-install-the-certificate"></a>Para instalar o certificado manualmente 

1. Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque o 4 de superfície no modo de administração (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
3. Execute o seguinte comando:
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a>Ingressar em um domínio do Active Directory (Opcional)
<a name="Certs"> </a>

Você pode ingressar em dispositivos do Skype sala sistemas v2 para o seu domínio. Dispositivos de v2 Skype sala sistemas devem ser colocados em uma UO separada estações de trabalho do seu PC porque muitos políticas de estação de trabalho não são compatíveis com sistemas de sala Skype v2. Um exemplo comum são as diretivas de aplicação da senha que impeça os sistemas de sala Skype v2 seja iniciado automaticamente. Para obter informações sobre o gerenciamento de configurações do GPO, consulte [gerenciar sistemas de sala Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md). 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>Para fazer o Skype Room Systems versão 2 ingressar em um domínio

1. Sinal de login no console do que o administrador da conta (consulte [gerenciamento de dispositivo e modo de Admin](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
2. Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.
    
3. Digite o seguinte comando no Powershell:
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e quiser que seus dispositivos de v2 Skype sala sistemas estejam em uma "sala Skype sistemas v2" UO que é um filho de uma unidade Organizacional "recursos", o comando será:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se você gostaria de renomear o computador ao ingressarem-lo a um domínio, use o sinalizador - NewName seguido pelo nome do novo do computador.
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Lista de verificação de implantação do Skype Room Systems versão 2
<a name="Checklist"> </a>

Use a lista de verificação a seguir ao fazer uma verificação final de que o dispositivo de console e todos os seus periféricos estão completamente configurados:
  
**Configurações do aplicativo**

|||
|:-----|:-----|
|☐  <br/> |O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console  <br/> |
|☐  <br/> |O nome do computador Windows está definido corretamente (útil para administração remota)  <br/> |
|☐  <br/> |A senha da conta do administrador foi definida e verificada  <br/> |
|☐  <br/> |Todas as atualizações de sistema do Surface Pro 4 ou do Surface Pro foram aplicadas  <br/> |
   
**Periféricos de áudio/vídeo**

|||
|:-----|:-----|
|☐  <br/> |A versão do firmware do periférico da câmera está correta (se aplicável)  <br/> |
|☐  <br/> |Câmera funcional e forma ideal posicionada  <br/> |
|☐  <br/> |Configurações do dispositivo de reprodução padrão e reprodução de dispositivo de comunicação padrão definida como áudio pretendido periféricos  <br/> |
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
   
## <a name="see-also"></a>Ver também
<a name="Checklist"> </a>

[Planejar a sala Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar Skype sala v2 de sistemas](room-systems-v2.md)
  
[Configurar um console v2 de sistemas de sala do Skype](console.md)
  
[Gerenciar Skype sala v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)