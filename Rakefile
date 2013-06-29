input_dirs = FileList["src/*"]
box_names = input_dirs.pathmap("%f")

directory "boxes"

box_names.each do |box_name|

  box_dir = "src/#{box_name}"
  box_file = "boxes/#{box_name}.box"

  file box_file => ["boxes"] + FileList["#{box_dir}/*"] do
    sh "tar -cv -C #{box_dir} -f #{box_file} ."
  end

  task box_name => box_file
  task :default => box_name

  desc "Add #{box_name} box to Vagrant"
  task "add:#{box_name}" do
    sh %(vagrant box add --force --provider aws #{box_name} boxes/#{box_name}.box)
  end

  task :add => "add:#{box_name}"

end

task :clean do
  sh "rm boxes/*.box"
end
