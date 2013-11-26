require "rabbit/task/slide"

# Edit ./config.yaml to customize meta data

spec = nil
Rabbit::Task::Slide.new do |task|
  spec = task.spec
  task.spec.files += Dir.glob("images/**/*.*")
  # task.spec.files -= Dir.glob("private/**/*.*")
  task.spec.add_runtime_dependency("rabbit-theme-groonga")
end

desc "Tag #{spec.version}"
task :tag do
  sh("git", "tag", "-a", spec.version.to_s, "-m", "Publish #{spec.version}")
  sh("git", "push", "--tags")
end
