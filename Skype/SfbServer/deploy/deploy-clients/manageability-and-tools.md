---
title: Skype gerenciamento e ferramentas do Sistema de Sala
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para saber mais sobre ferramentas de gerenciamento para Skype Room System.
---

# <a name="skype-room-system-manageability-and-tools"></a>Skype gerenciamento e ferramentas do Sistema de Sala
 
Leia este tópico para saber mais sobre ferramentas de gerenciamento para Skype Room System.
  
## <a name="administrative-portal"></a>Portal Administrativo

Para Skype for Business Server implantações locais, você pode usar o portal administrativo do Sistema de Sala Skype para gerenciar e monitorar ativamente Skype implantações do Sistema de Sala em sua organização.
  
Confira o artigo a seguir para obter mais detalhes:
  
- [Implantar o SRS v1 Administrative Web Portal em Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange Checklist

- Confirme se a Descoberta Automática está configurada e um REGISTRO DNS A/CNAME interno está disponível para autodiscover.domain.com.
    
- Descoberta automática de ping (por exemplo, Ping Autodiscover.contoso.com).
    
- Teste seu serviço de Descoberta Automática com a Ferramenta analisador de Conectividade da Microsoft. Escolha o primeiro teste, "Não posso fazer logoff com Office Outlook".
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o sistema de sala Skype (script de exemplo na parte inferior da página).
    
## <a name="skype-for-business-checklist"></a>Skype for Business Lista de Verificação

- Execute as seguintes ferramentas:
    
  - Skype for Business Analisador de Práticas Recomendadas     
  - Skype for Business Ferramenta de Análise de Saúde (Excel)    
  - Skype for Business Analisador de Conectividade de 32 bits ou 64 bits
    
- Revise [Ferramentas úteis de solução de problemas e análise para Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365). Confirme se você tem um pool Skype for Business e um servidor Office Web Apps e pode compartilhar um PowerPoint usando o Skype for Business cliente.
    
- Se a sala de reunião já tiver uma caixa de correio de recurso, habilita-a para Skype for Business.
    
- Se necessário, solicite um DID (número de telefone) para o sistema Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.
    
## <a name="network"></a>Rede

- Certifique-se de ter uma conexão de rede com fio para o Skype Room System.
    
- Leia o Guia de Planejamento de Rede para Skype for Business.
    
- Solicite uma Skype for Business de rede de um Skype for Business parceiro.
    
- Leia os dados de desempenho capturados na ferramenta Skype for Business Análise de Saúde (Excel).
    
- Execute a Ferramenta de Análise de Rede.
    
- Execute a Ferramenta de Diagnóstico de Pré-Chamada.
    
## <a name="skype-room-system-security"></a>Skype do sistema de sala

Skype Room System é um sistema incorporado que pode ser totalmente integrado em uma implantação Windows, usando o modelo de segurança Skype for Business, gerenciamento de direitos e ferramentas de gerenciamento, como SCOM. Os recursos incluem:
  
- Um Filtro de Gravação para impedir gravações de disco no modo de usuário 
    
- App Locker para impedir a execução de aplicativos não autorizados. Todas as portas USB estão desabilitadas no modo de usuário.
    
  - Nenhum aplicativo padrão ou visualizadores reside no hardware Skype Sistema de Sala. Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.
    
  - O computador do dispositivo executa o Windows sistema operacional Embedded Standard 7. Todo o hardware, incluindo dispositivos, é fornecido por parceiros OEM.
    
  - A junção de domínio opcional aos Serviços de Domínio do Active Directory (AD DS), habilitando o gerenciamento e o controle de contas de segurança locais.
    
- Você também pode gerenciar a conta de administrador local usando o Skype for Business de administração.
    
- Skype Room System é atualizado por meio de processos padrão do Microsoft Update.
    
- Skype Room System se conecta com Skype for Business.
    
  - Skype for Business usa criptografia de ponta a ponta e autorização para todos os modos de comunicação
    
  - Skype Room System oferece suporte Skype for Business padrões de segurança e conformidade. Consulte [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) para obter mais informações.
    
## <a name="license"></a>Licença

Verifique se você usa um KMS para ativar software. Em caso afirmado, talvez seja necessário verificar ou adicionar a chave Skype for Business cliente KMS a ele. Se você não estiver usando KMS, solicite a chave de licenciamento por volume para o mak Skype for Business cliente.
  
## <a name="license-keys"></a>Chaves de licença

Skype Room System executa o cliente Skype for Business área de trabalho em segundo plano. Se Skype Room System for um membro de domínio, ele descobrirá sua KMS. (e se ele tiver a chave de licenciamento por volume KMS ela será ativada automaticamente). O Licenciamento por Volume também fornece um MAK, que você insinte à medida que exibe xxxxx-xxxxx-xxxxx-xxxxx-xxxxx. (Você precisa de acesso à Internet para ser ativado usando MAK, mas não KMS). Para obter mais informações, consulte Ativação de volume Office 2013.
  
- Para inserir a chave MAK, vá para OEM Configurações Ferramenta de Licenciamento \> srs. Clique em Verificar Status. Quando o status diz "o produto não está ativado", digite a tecla.
    
- Se durante a ativação você receber um erro que diga "'O Serviço de Licenciamento de Software reportou que a chave do produto é inválida", verifique se:
    
  - A chave foi inserida corretamente.
    
  - Você entrou na tecla Skype for Business MAK e não outra chave.
    
  - O sistema tem acesso à Internet.
    
- Você pode ativar por telefone, mas deve ter tentado ativar usando a Ferramenta de Licenciamento srs primeiro. Para ativar por telefone, inicie uma reunião de teste (não uma chamada de teste, pois é muito curta). No Assistente Office de Ativação de Telefone, chame a Microsoft, digite o número longo e insira uma resposta.
    
## <a name="certificate-authority"></a>Autoridade de Certificação

Confirme se a Autoridade de Certificação usada para emitir o certificado Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade Lista de Certificados revogados.
  
Importe o arquivo Certificate (.crt) para o Skype Room System se estiver usando Skype for Business Server. Ele é facilmente obtido do compartilhamento CertEnroll do servidor ca ou na pasta Raiz Confiável de qualquer computador ingressado no domínio.
  
## <a name="certificates"></a>Certificados

Verifique se a Autoridade de Certificação tem um caminho http para a Lista de Revogação de Certificados. Caso não seja, atualize sua AC para incluir um.
  
Instale certificados na configuração de administrador do Skype Room System em System Configurações \> Certificate Manager. Você precisa da Enterprise raiz do certificado interno.
  
Uma maneira de obter os certificados necessários é descobrir a AC que emitiu seus certificados. Para Skype for Business Server, em um computador em Skype for Business, clique Configurações \> Ferramentas \> discar em Conferência Configurações. Isso abre uma página da Web protegida pela AC que emitiu os certificados internos. Clique no ícone Bloquear na barra de endereços do navegador para exibir um relatório de segurança. Clique em Exibir Certificados e examine a propriedade Ponto de Distribuição crl. O segundo parâmetro CN deve ser o nome do servidor da AC. Agora abra Windows Explorer para esse endereço \\\< CA Server Name \>\CertEnroll. Copie os dois arquivos .crl e o arquivo .crt para uma unidade flash e coloque-o no lado esquerdo da placa SMART.
  
Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.
  
Importe os arquivos .crl no sistema de sala Skype na pasta Autoridades intermediárias de certificados. (Você precisa alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para ver os arquivos).
  
Observação: o servidor Office Web Apps 2013 pode compartilhar a mesma CA que Skype for Business. Se não for, você não poderá compartilhar PowerPoint em uma reunião. Verifique com a IT e obtenha os arquivos CRT e CRL do compartilhamento de rede da CA CertEnroll conforme explicado acima. 
  
A associação de domínio pode simplificar algumas coisas porque você pode tratar o sistema de sala Skype como um sistema de Windows e ele pode contar com o Active Directory para alguns dos aspectos do certificado. No entanto, é melhor gerenciar isso manualmente.
