require "docraptor"

desc 'Convert HTML to PDF'
task :pdf do
  DocRaptor.configure do |config|
    config.username = "FBcFMylmCiZv4S60JOR9"
  end

  $docraptor = DocRaptor::DocApi.new

  $docraptor.create_doc(
    document_url: "https://mansakondo.github.io/",
    name: "resume",
    document_type: "pdf",
    javascript: true
  )
end
