
Você pode melhorar sua Salas do Teams de reunião personalizando como a conta de recurso responde e processa convites de reunião. Usando Exchange Online PowerShell, você pode definir as seguintes propriedades da conta de recurso:

- **AutomateProcessing: `AutoAccept`** Os organizadores da reunião recebem a decisão de reserva da sala diretamente sem intervenção humana.

- **AddOrganizerToSubject: `$false`** O organizador da reunião não é adicionado ao assunto da solicitação de reunião.

- **DeleteComments: `$false`** Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada. Isso é necessário para processar equipes externas e reuniões de terceiros para fornecer uma experiência de Ingresso no One Touch.

- **DeleteSubject: `$false`** Mantenha o assunto das solicitações de reunião recebidas.

- **ProcessExternalMeetingMessages: `$true`** Especifica se as solicitações de reunião devem ser processadas que se originam fora da organização do Exchange. Necessário para reuniões externas do Teams e [reuniões de terceiros](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Garante que o sinalizador privado que foi enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.

- **AddAdditionalResponse: `$true`** O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.

- **AdditionalResponse: "Esta é uma sala de reunião do Microsoft Teams!"** O texto adicional a ser adicionado à resposta de aceitação da reunião.

Para configurar essas propriedades, você precisa se conectar ao Exchange Online PowerShell. Para obter mais informações, [consulte Conectar-se Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

Depois de se conectar ao Exchange Online PowerShell, você pode configurar as propriedades da caixa de correio em uma conta de recurso usando o cmdlet [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

O exemplo a seguir define as propriedades da conta `ConferenceRoom01` de recurso:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

